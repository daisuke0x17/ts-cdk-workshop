## AWS CDK Workshop
### プロジェクトの構造
- `lib/cdk-workshop-stack.ts`
CDKアプリケーションのメインスタックが定義される。今回のワークショップでほとんどの時間を費やすことになるファイル。
- `bin/cdk-workshop.ts`
CDKアプリケーションのエントリポイント。`lib/cdk-workshop-stack.ts` で定義されたスタックをロードする。
- `cdk.json`
アプリの実行方法をツールキットに指示させるためのファイル。今回の場合は、`"npx ts-node bin/cdk-workshop.ts"`。

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
