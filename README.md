EC2でHLDS動かすための適当テンプレート。  
結局少し試してやめたので完成してない。

TODO: ネットワークACLのあけるポートが足りてなくてSteamCMDのゲームインストールが上手く行かない。


```sh
aws cloudformation create-change-set \
    --template-body file://templates/stack-vpc.yml \
    --cli-input-json file://parameters/stack-vpc.json \
    --change-set-type CREATE

aws cloudformation create-change-set \
    --template-body file://templates/stack-security-group.yml \
    --cli-input-json file://parameters/stack-security-group.json \
    --change-set-type CREATE

aws cloudformation create-change-set \
    --template-body file://templates/stack-ec2.yml \
    --cli-input-json file://parameters/stack-ec2.json \
    --change-set-type CREATE
```
