# IdeaDock
## 参考
### 環境構築(Docker) 
- [Docker超入門講座](https://youtube.com/playlist?list=PLs3eD4QT7ow6O5wyRRnRCvB7JMuq_D3-D&si=SKyi4JGlcTIOVq-A)
### fontend
- [基礎編](https://youtube.com/playlist?list=PLX8Rsrpnn3IWPoM7-1YPDksRRkamRY25k&si=zItwrMcGJpVi5-pQ)
- [Next.js App Router 入門](https://youtube.com/playlist?list=PLX8Rsrpnn3IVn8wAxWL2yTMDrqF0vHccO&si=PCbaL4rrII7H_nea)
- [Nextjs リファレンス](https://nextjs.org/docs)
## 時間
- 環境構築(Docker):2~3日
- frontend(Next.js)
  - メモ機能:1~3日 (理想7日)
## 環境構築
- 初期化
  - frontend
    - docker compose up frontend-init --abort-on-container-exit
  - backend
    - docker compose up frontend-init --abort-on-container-exit
- 開発用
  - docker-compose build
  - docker-compose up -d
  - frontend
    - docker start frontend
    - docker exec -it frontend /bin/bash
  - backend
    - docker start backend
    - docker exec -it backend /bin/bash
## Todo
  - front
    - メモ機能
      - 思いつきを即座に保存（スマホ・PC問わず）
      - メモをタグやキーワードではなく「自動で構造化」したい（Zettelkasten）
      - ToDo やプロジェクト、ブログ、家計簿などの起点になるメモである
      - 音声・URL・画像も含めて柔軟に保存したい
      - 何に使うかわからないメモも、後から発掘・活用したい

