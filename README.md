# apache-kafka-test

## 手順
1. ./gradlew composeUpで、zookeeperとkafkaのイメージからコンテナを立ち上げる。
2. docker-compose psで本当に立ち上がっているか確認する。
3. docker container exec -it apache-kafka-test_kafka_1 bashでコンテナに入る。
4. コンテナの中でcd /でrootに移動する。
5. コンテナの中でbin/kafka-console-consumer --bootstrap-server localhost:9092 --topic mytopic --from-beginningでConsumerを起動する。
6. 自分のPCのターミナルに戻る。
7. ./gradlew runでProducer用プログラムを起動する。
8. コンテナの中を再び確認すると、メッセージを消費していることが分かる。
9. ./gradlew composeDownでdockerのコンテナを正常に終了する。

## 起動
```
./gradlew composeUp
```

## 終了
```
./gradlew composeDown
```

