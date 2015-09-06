# todoApp

## AngularJS
- ng-app
  - Angularアプリケーションである事の宣言。読み込むモジュール名を指定する
    - 今回の場合はtodoApp
- ng-controller
    - `<div ng-controller="TodoListController as todoList">`
      - TodoListController というコントローラーを todoList という別名を付けて使用することを宣言している
        - 別名をつける理由は繰り返し使用する名前を短くするため
      - divタグで宣言することで、そのdivタグ内の子要素でTodoListControllerに記載された内容を使用することが出来る
- {{todoList.remaining()}}
  - {{}}で囲った中でコントローラーに記載された内容を表示することが出来る。todo.jsのtodoList.remainingの実行結果を記載可能
- ng-repeat
  - `<li ng-repeat="todo in todoList.todos">`
    - todo はここで使用を宣言する変数名みたいなもの
    - todo in A で Aを対象とする事を宣言
- `<input type="checkbox" ng-model="todo.done">`
  - input type="checkbox は ふつうのHTML
  - ng-modelを付けて、状態変化の制御先を指定する
- `<span class="done-{{todo.done}}">`
  - タスクが完了状態になった時に見た目を変更する
  - class名にデータを反映させ、class名をデータ変更に追従して変更する。class名によってcssに記載した内容が適応され、取り消し線とグレーアウトが表示される。
- `<pre>{{todo|json}}</pre>`
  - データを表示するためのおまじない。デバッグ用。
- todoList.todos.push
  - todoLis.todos に要素を追加

## メモ
- 課題
  - omniFocusの要素を取り入れてみる
    - タスク単体
      - コンテキスト
      - メモ
      - 期限
      - プロジェクト
      - 延期
    - 全体
      - タスクのネスト
      - 検索
      - 絞込表示
      - プロジェクトビュー
      - コンテキストビュー
  - アプリケーションとしての実用性
    - データの永続性(これはサーバーサイドをいじれる様になってから？)
    - 見た目
    - 操作性

## 未整理
- [angular.forEach](http://js.studio-kingdom.com/angularjs/ng_global_apis/angular_foreach)
- [ng-repeat](http://js.studio-kingdom.com/angularjs/ng_directive/ng_repeat)

### mvc

### メモ
- フィルター
- ループ
- html pre
  - 半角スペースや改行をそのまま表示
- バリデーション
  - ng-show
  - ng optionがAPIドキュメントがあるので参照
- 実装課題
  - とりあえずomniFocusの機能を1つずつ実装してみるのは？


<li ng-repeat="todo in todoList.todos">
todo は命名に近い

### フィルター
<li ng-repeat="todo in todoList.todos|filter:'learn'">

### 順番
<span class="done-{{todo.done}}">{{$index+1}} {{todo.text}}</span>
index/first/middle/last

### 偶数奇数
ng-class-even ng-class-odd

## 07 コントローラーのネストとイベント
