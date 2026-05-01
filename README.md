# 🎯 Spring Boot TODO App

JavaとSpring Bootで構築した、シンプルなTODOアプリケーションです。H2データベースを使用しています。

## 📋 機能

- ✅ TODOの作成・読取・更新・削除 (CRUD)
- ✅ 完了/未完了でのフィルタリング
- ✅ タイトルでのTODO検索
- ✅ RESTful API エンドポイント
- ✅ H2 インメモリ データベース
- ✅ H2 コンソール で DB を確認

## 🛠️ 技術スタック

- **Java 17**
- **Spring Boot 3.2.0**
- **Spring Data JPA**
- **H2 Database**
- **Maven**
- **Lombok**

## 📁 プロジェクト構成

```
todo-app/
├── pom.xml
├── README.md
└── src/main/
    ├── java/com/example/todoapp/
    │   ├── TodoAppApplication.java     # メインクラス
    │   ├── controller/TodoController.java   # REST API
    │   ├── service/TodoService.java        # ビジネスロジック
    │   ├── repository/TodoRepository.java  # データアクセス
    │   └── model/Todo.java                 # エンティティ
    └── resources/
        ├── application.properties
        └── data.sql
```

## 🚀 クイックスタート

### 前提条件

- Java 17 以上
- Maven 3.6 以上

### インストール

```bash
git clone https://github.com/daigo-fujiwara/todo-app.git
cd todo-app
```

### アプリケーション起動

```bash
mvn clean install
mvn spring-boot:run
```

アプリケーションは `http://localhost:8080` で起動します。

## 📡 API エンドポイント

### 全TODOを取得
```bash
GET /api/todos
```

### 特定のTODOを取得
```bash
GET /api/todos/{id}
```

### TODOを完了ステータスで検索
```bash
GET /api/todos?completed=false
GET /api/todos?completed=true
```

### TODOをタイトルで検索
```bash
GET /api/todos?search=Learn
```

### TODOを作成
```bash
POST /api/todos
Content-Type: application/json

{
  "title": "New TODO",
  "description": "TODO の説明"
}
```

### TODOを更新
```bash
PUT /api/todos/{id}
Content-Type: application/json

{
  "title": "Updated Title",
  "description": "Updated description",
  "completed": true
}
```

### TODOを削除
```bash
DELETE /api/todos/{id}
```

## 🗄️ H2 コンソール

H2 データベースコンソールにアクセス：

```
http://localhost:8080/h2-console
```

**接続情報:**
- JDBC URL: `jdbc:h2:mem:testdb`
- User Name: `sa`
- Password: (空白)

## 📝 cURL コマンド例

### すべてのTODOを取得
```bash
curl http://localhost:8080/api/todos
```

### TODOを作成
```bash
curl -X POST http://localhost:8080/api/todos \
  -H "Content-Type: application/json" \
  -d '{"title": "Learn Spring Boot", "description": "Study Spring Boot"}'
```

### TODOを更新
```bash
curl -X PUT http://localhost:8080/api/todos/1 \
  -H "Content-Type: application/json" \
  -d '{"title": "Updated Title", "description": "Updated", "completed": true}'
```

### TODOを削除
```bash
curl -X DELETE http://localhost:8080/api/todos/1
```

## 🧪 テスト

```bash
mvn test
```

## 📚 参考資料

- [Spring Boot Documentation](https://spring.io/projects/spring-boot)
- [Spring Data JPA](https://spring.io/projects/spring-data-jpa)
- [H2 Database](https://www.h2database.com/)

## 📄 ライセンス

このプロジェクトはMITライセンスの下でライセンスされています。

## 👤 作成者

daigo-fujiwara
