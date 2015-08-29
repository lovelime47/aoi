# Aoi
Aoi Framework (Asynchronous Object Interface)

Aoi Framework aims to be elegant software architecture for iOS and other mobile environment.
Aoi Framework は iOS をはじめとするモバイル開発環境での洗練されたソフトウェア設計を目指したものです。

Aoi's comcept is 'Asynchronous' and 'Object Interface'.
Aoi のコンセプトは 「非同期性」と「オブジェクトのインターフェースです」

'Asynchronous' is very important for mobile software. Because mobile hardwares have low speed network. User should always get responce even processing and transfering while. 
「非同期性」は低速なインターネット回線をもつモバイル端末には重要な要素です。たとえ処理中や通信中であっても、ユーザーは常にレスポンスが得られるようにするべきです。

'Object Interface' is very important for all software especially, how to transform data between view controller and business logic and other view controllers in architecture for mobile software. Bad object interface make difficult changing and meintenancing.
「オブジェクトのインターフェース」は全てのソフトウェアにとって重要な事柄です。そのなかでも特にビューコントローラーとビジネスロジック、あるいはビューコントローラーと他のビューコントローラーの間でどのようにデータを受け渡すかというのは、モバイルソフトウェア設計において得意に重要です。良くないオブジェクト間インターフェースはソフトウェアの変更や運用を難しくしてしまいます。

Aoi implement 'Asynchronous' and 'Object Interface' with shared memory and notification and GCD(Grand Central Dispatch).
Aoi ではこの「非同期性」と「オブジェクト間のインターフェース」を共有メモリ・通知・GCD（Grand Central Dispatch）によって実現します。

In Aoi, In some case, business logic doesn't return result data but set result data to shared memory and notify finished asynchronously. It enable caller is not receiver. When API data recived form server, app should affect API data all view controller. Caller doesn't know what view controller update with recived data and doesn't have responsible to transfer data to other view controllers.
Aoi ではビジネスロジックが直接結果をリターンするのではなく、共有メモリに結果をセットし、非同期に完了を通知する事があります。これによって、呼び出し元以外のビューコントローラーがデータを受け取る事ができます。呼び出し元はどのビューコントローラーが同じデータを必要としているかわかりません。そのため、受信したデータをそのデータを必要としているビューコントローラーに渡すこともできません。

For example, calender and mail and messanger application send data to server and all client get updated data and print the data.
例としてカレンダー、メール、メッセンジャーなどのアプリケーションはサーバーにデータを送信し、すべてのクライアントがデータ更新の通知をうけ、最新のデータを表示します。

Mobile application's view controllers need this level of independance.
モバイルアプリケーションのビューコントローラーはにはこのレベルの独立性が必要になります。

Deviding app to each independant viewcontroller by shared memory and synchronous notification make app more simple and tastable.
共有メモリと非同期通知によってアプリは独立したビューコントローラーに分割され、この分割はアプリケーションをよりシンプルに、テスト可能にします。
