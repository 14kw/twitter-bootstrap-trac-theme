Twitter Bootstrap Trac Theme
======================
Twitter Bootstrapを利用したTracのテーマです。  
似たようなテーマはいくつかありましたが、バージョンが合わなかったり、  
スタイルが個人的に合わなかったりしたので作成しました。

利用バージョン
-----

* Trac1.0.1
* Twitter Bootstrap Version2.3.1

使い方
-----
patchファイルを作るのがめんどくさかったので、基本的に上書きして使います。  
Trac本体にもclassを付けたかったので手を入れています。
 
### Tracのソースを上書きしてインストール ###
    # git clone https://github.com/14kw/twitter-bootstrap-trac-theme.git
    # wget http://download.edgewall.org/trac/Trac-1.0.1.tar.gz
    # tar xvfz Trac-1.0.1.tar.gz
    # cd Trac-1.0.1
    # cp ../twitter-bootstrap-trac-theme/trac_src/Trac-1.0.1/trac/* ./trac/
    # easy_install babel
    # python setup.py install


### Tracの共通ファイルをコピー ###
    # cp ./twitter-bootstrap-trac-theme/trac_common /usr/share/trac
    # vi $TRAC_ROOT/conf/trac.ini
    [header_logo]
    src = /trac_common/trac_banner.png
    
    [inherit]
    file = /usr/share/trac/conf/trac.ini
    
    [project]
    icon = /trac_common/trac.ico
    
    [trac]
    htdocs_location = /trac_common
    
    # vi $APACHE_ROOT/conf/httpd.conf
    Alias /trac_common /usr/share/trac/htdocs

スクリーンショットとサンプルTrac
-----

* http://14code.com/blog/wp-content/uploads/2013/06/twitter-bootstrap-trac-theme_screenshot.png
* http://14code.com/trac/test01


日本語化について
-----
レポートの日本語化については、[インタアクト株式会社](http://www.i-act.co.jp/project/products/products.html "インタアクト株式会社")が公開している、Trac-1.0.ja1を流用させてもらいました。  
デフォルトのwikiも日本語化させたい方は、trac/wiki/default-pages 配下も上書きしてください。

参考にした他テーマ
-----
* https://github.com/chevah/trac-bootstrap-theme/
* http://trac.edgewall.org/


更新情報
-----
* 2013/06/18：見た目が整ったので公開
 * プラグインにより作成される画面は表示が崩れる場合があります
 * （ある程度は個人的にも使うのでフォローするつもりです）

