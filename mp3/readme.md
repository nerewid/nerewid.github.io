元の音源が入ったフォルダで以下を実行

//無音除去
find . -name  *.mp3 -exec sox {} ../no_initial_silence2/{} silence 1 0.01 5.0% : restart \;

//上の無音除去で何故か最初に0.025秒ほどの無音が追加されてしまうので、オフセットを0.025にしてそこから0.1~1.0秒切り出す
find . -name  *.mp3 -exec sox {} ../0.1/{} trim 0.025 0.1 \;
find . -name  *.mp3 -exec sox {} ../0.2/{} trim 0.025 0.2 \;
find . -name  *.mp3 -exec sox {} ../0.3/{} trim 0.025 0.3 \;
find . -name  *.mp3 -exec sox {} ../0.5/{} trim 0.025 0.5 \;
find . -name  *.mp3 -exec sox {} ../1.0/{} trim 0.025 1.0 \;