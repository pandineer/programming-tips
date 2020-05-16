You can use struct or class defined by yourself as key of std::map of C++.
Here, how to use struct defined by myself as key of std::map is introduced.

Among keys need to be comperable to find specified file from map, because std::map stores data as binary tree.
So not only data but also comparison operator need to be defined for struct defined by myself.

Here, sample code which uses int and char[100] struct as key is introduced.
Of course, there is another implementation of comparison operator.

It is required that comparison operator need to be defined to be able to decide small or large clearly.

# C++のstd::mapのキーに、自分で定義した構造体やクラスを使うことができます。
# ここでは、自分で定義した構造体を、std::mapのキーとして使う方法を紹介しています。
# std::mapはデータを二分木で格納しているおり、map内から指定されたファイルを探すことができるようにするために、キー同士を比較できる必要があります。
# よって、自分で定義した構造体に、データだけでなく、比較演算子<を定義してあげる必要があります。

# ここで紹介しているサンプルコードは、intとchar[100]を持った構造体をキーとしたい場合のサンプルです。
# もちろん、比較演算子の処理の書き方は、ここで紹介している方法に限りません。

# ただ一点注意しなければならないのが、比較演算子は適切に大小を比較できるように定義してあげなければいけません。
当たり前じゃないかと思われるかもしれませんが、筆者は一度、ここで落とし穴にはまってしまい、デバッグに時間がかかったことがあります。。
極端な話、intのキーに対して0だったらfalse、それ以外はtrueを返す、というような処理にしちゃうと、正しく比較できなくなり、正常に取り出すことはおろか、格納することすらできなくなってしまうと思います。
恐ろしいのは、コンパイルはそれでも通りますし、一つ目のデータは問題なく格納も取り出すこともできてしまうとこです。
自分で定義した構造体やクラスをmapのキーにして動作がおかしかったら、まずは比較演算子の処理の中身を疑ってみるといいかも知れません。