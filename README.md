【ご確認依頼】ui-bffのdocker-compose.yaml変更（PR #261）に伴うコンテナ再作成のお願い

お疲れ様です。
PR #261（DifyのAPIキー・接続先を環境変数で管理する）のマージに伴い、frontend_server/ui-bff/docker-compose.yamlに変更が入ります。

ui-bffのコンテナを立てっぱなしにしている方は、最新のmainを取り込んだ後に docker compose up --build を再実行してください。（docker compose restartでは変更が反映されません）

変更点：

環境変数 DIFY_API_BASE_URL / DIFY_API_KEY を追加
extra_hosts に host.docker.internal:host-gateway を追加（同一ホスト上のDifyへ接続するため）

現時点ではDify呼び出し自体は未実装（#244で対応予定）のため、今すぐ何かが壊れるわけではありません。ただし設定を正しく反映させるため、上記の再起動（再作成）をお願いします。
