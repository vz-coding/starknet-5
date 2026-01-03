## Step 0

使用 [Scaffold Stark](https://scaffoldstark.com/) 从模版创建新项目

```bash
npx create-stark@latest
```

依次执行以下命令在本地启动项目:

```
yarn chain
yarn deploy
yarn start
```

在浏览器中打开 http://localhost:3000 预览

## Step 1

从 week-3 目录添加 Counter 合约，并更新位于 `packages/snfoundry/scripts-ts/deploy.ts` 的部署脚本

重新部署合约：`yarn deploy`

## Step 2

通过前端 Debug 控制台测试合约功能

## Step 3

为合约增加 dec 方法，令计数器自减

并将数字改为允许算数溢出的类型

## Step 4

使用如下 Hook，更新主页 `packages/nextjs/app/page.tsx` 内容，为合约开发简易前端

```typescript
import { useTargetNetwork } from "~~/hooks/scaffold-stark/useTargetNetwork";
import { useBlockNumber } from "@starknet-react/core";
import { useDeployedContractInfo } from "~~/hooks/scaffold-stark";
import { useScaffoldReadContract } from "~~/hooks/scaffold-stark/useScaffoldReadContract";
import { useScaffoldWriteContract } from "~~/hooks/scaffold-stark/useScaffoldWriteContract";
import { useScaffoldEventHistory } from "~~/hooks/scaffold-stark/useScaffoldEventHistory";
```

参考文档：
- https://www.starknet-react.com/
- https://scaffoldstark.com/docs

参考实现: [`DemoCounter.tsx`](./DemoCounter.tsx)