# C#でEntity(MySQL)を使う
## 環境
- Windows7 64bit
- VisualStudio community 2015

## インストール
SQLServerは元から利用できるが、MySQLは
利用できない。
インストールする
- URL:http://dev.mysql.com/downloads/windows/visualstudio/

本ファイル作成時点でのバージョンは
1.2.5なのでこれ以上のバージョンならＯＫ
かと思います。
## エンティティを参照追加
- MySQL.Data
- MySQL.Data.Entyty
無ければnugetすればよいと思うよ！

## エンティティを追加
新規項目でエンティティを追加する
適当にウィザードに従っていけばよい。

## DataGridViewにSelect結果を表示
```csharp
worldEntities1 worldEntities = new worldEntities1();
var load = from g in worldEntities.city select g;
if(load != null)
{
    dataGridView1.DataSource = load.ToList<city>();
}
```
### 注意(はまりどころ)
作ったエンティティ(edmx)と実際に使う
クラス名が異なってくる。
クラスはエンティティ名.Context.csにて
実装されているので参照すればよろし。

# 参照
- http://dev.mysql.com/downloads/windows/visualstudio/
- http://www.codeproject.com/Tips/426790/Using-MySQL-with-Entity-Framework
- http://www.moonmile.net/blog/archives/2823
- https://blogs.oracle.com/MySqlOnWindows/entry/you_can_use_mysql_for
- http://stackoverflow.com/questions/22031269/enable-entity-framework-6-for-mysql-c-in-winforms-of-microsoft-visual-studio
