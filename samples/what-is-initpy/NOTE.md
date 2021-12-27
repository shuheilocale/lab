# What is `__init__.py` ?

## Resources

- `[jp]`
  - [Python の __init__.py とは何なのか | Qiita](https://qiita.com/msi/items/d91ea3900373ff8b09d7)
- `[en]`


## What is `__init__.py` for ?

`__init__.py` の役割とは以下である。

1. `__init__.py` は、モジュール検索のためのマーカーとなる。 **--> sample01**
2. `__init__.py` は、それが存在するディレクトリ名を名前とする名前空間の初期化を行う。 **--> sample02**
3. `__init__.py` は、同、名前空間におけるワイルドカード import の対象を定義する (`__all__` の定義) 。 **--> sample03**
4. `__init__.py` は、同じディレクトリにある他のモジュールの名前空間を定義する。 **--> sample04**


## Notes

> サンプル2 では、module02 を呼び出すのに、dir/ というディレクトリがあるために、dir.module02 という名前空間で参照する必要がありました。
> dir が邪魔ですね。実体がないのに、名前空間の階層として指定しなければなりません。
>
> そこで登場するのが、__init__.py。
> ディレクトリ階層にした上で、直接、module02 という名前で呼び出す方法が __init__.py です。

> つまり、dir/module02.py の代わりに module02/__init__.py の中にプログラムを書くことで、module02 として呼び出せるようになります。

> __init__.py を置いた場合には、ディレクトリ名と同じ名前空間の実体モジュールとして扱われています。
> もう少し違う言い方をすれば、__init__.py は、ディレクトリ名をモジュール名(あるいは明示的な「名前空間」)としてマッピングするためのファイル、と言えます。(ディレクトリ名を名前空間としたときのコンストラクタの役割)


| No. |namespace type|construction|
|---|---|---|
|1| `class` | `def __init__(self)` |
|2| `dir module` | `__init__.py` |
