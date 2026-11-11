【ご確認依頼】ui-bffのdocker-compose.yaml変更（PR #261）に伴うコンテナ再作成のお願い

お疲れ様です。
PR #261（DifyのAPIキー・接続先を環境変数で管理する）のマージに伴い、frontend_server/ui-bff/docker-compose.yamlに変更が入ります。

ui-bffのコンテナを立てっぱなしにしている方は、本日中にdocker compose up --buildを再実行してください。（docker compose restartでは変更が反映されません）

変更点：

環境変数 DIFY_API_BASE_URL / DIFY_API_KEY を追加
extra_hosts に host.docker.internal:host-gateway を追加（同一ホスト上のDifyへ接続するため）

本日中にDify呼び出し自体の実装（#244）を進める予定です。実装後は、コンテナを再作成していないと新しい設定（環境変数・extra_hosts）が反映されず、Dify呼び出し部分でエラーになります。また、DIFY_API_KEYは各自の.envにまだ設定されていないため（.env.exampleは更新済み）、あわせて設定をお願いします。

お手数ですが、本日中の対応をお願いします。
