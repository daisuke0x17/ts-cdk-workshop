## AWS CDK Workshop
### プロジェクトの構造
- `lib/cdk-workshop-stack.ts`
  - CDKアプリケーションのメインスタックが定義される。今回のワークショップでほとんどの時間を費やすことになるファイル。
- `bin/cdk-workshop.ts`
  - CDKアプリケーションのエントリポイント。`lib/cdk-workshop-stack.ts` で定義されたスタックをロードする。
- `cdk.json`
  - アプリの実行方法をツールキットに指示させるためのファイル。今回の場合は、`"npx ts-node bin/cdk-workshop.ts"`。

### cdk synth
`cdk synth` で CFｎ のテンプレートが出力される。
- AWS CDK アプリケーションは、事実上、コードを使用したインフラストラクチャの**定義**にすぎない
- CDK アプリケーションを実行すると定義されたスタックごとに CFn テンプレートが生成（ CDK 用語では「 合成 」）される

> **Note** 
> CDK CLI は cdk.json ファイルが配置されているプロジェクトのルートディレクトリで実行する必要がある

### cdk deploy
- `cdk bootstrap`
  - AWS CDK アプリケーションを環境 (アカウント/リージョン) に初めてデプロイするときは「 Bootstrap スタック」をインストールする必要がある
  - このスタックにはツールキットの操作に必要なリソースが含まれる
  - デプロイプロセス中にテンプレートとアセットを保存するための S3 バケットが含まれる
- `cdk deploy`
  - 各 CDK スタックは CloudFormation スタックと 1:1 でマッピングされる
  - CFn コンソールからスタックが確認できる

### cdk diff
- ツールキットによって CDK アプリケーションと現在デプロイされているものの差分を確認
- `cdk deploy` を実行したときに何が起こるかを確認するための安全な方法であり良い習慣

## Welcome to your CDK TypeScript project

You should explore the contents of this project. It demonstrates a CDK app with an instance of a stack (`CdkWorkshopStack`)
which contains an Amazon SQS queue that is subscribed to an Amazon SNS topic.

The `cdk.json` file tells the CDK Toolkit how to execute your app.

## Useful commands

* `npm run build`   compile typescript to js
* `npm run watch`   watch for changes and compile
* `npm run test`    perform the jest unit tests
* `cdk deploy`      deploy this stack to your default AWS account/region
* `cdk diff`        compare deployed stack with current state
* `cdk synth`       emits the synthesized CloudFormation template
