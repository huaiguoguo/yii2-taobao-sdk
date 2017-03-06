####yii2-taobao-sdk

####taobao-sdk-PHP-auto_1457166217151-20170221

####安装方法  composer require huaiguoguo/yii2-taobao-sdk:dev-master

####简单的使用方法

	use yii\taobao\top\request\TbkItemGetRequest;
	use yii\taobao\top\TopClient;

	$client            = new TopClient();
	$appkey    = Yii::$app->params['taobao']['phpdx']['appkey'];
	$appsecret = Yii::$app->params['taobao']['phpdx']['appsecret'];
	$client->appkey    = $appkey;
	$client->secretKey = $appsecret;
	$client->format    = 'json';
	$req = new TbkItemGetRequest;
	$req->setFields("num_iid,title,pict_url,small_images,reserve_price,zk_final_price,user_type,provcity,item_url,seller_id,volume,nick");
	$req->setQ("女装");
	$req->setCat("16,18");
	$resp = $client->execute($req);
	$str =  json_decode( json_encode( $resp),true);
	print_r(  json_encode($str) );

####更多使用方法请参考 http://open.taobao.com/docs/api_list.htm  相关文档

####Yii2更多学习请加群: [70324424](https://jq.qq.com/?_wv=1027&k=45gpuJu)

####Yii2社区: [http://www.phpdx.cn](http://www.phpdx.cn)
