## Step 0

使用 scarb 从模版创建合约项目

## Step 1

编写 Counter 合约，并实现以下方法

```
#[starknet::interface]
pub trait ICounter<TContractState> {
    fn get(self: @TContractState) -> u32;
    fn inc(ref self: TContractState);
}
```

## Step 2

为合约编写单元测试

## Step 3

为合约增加 constructor 函数，指定计数器初始值

提示：https://www.starknet.io/cairo-book/ch101-02-contract-functions.html#1-constructors

## Step 4

当计数器改变时，创建一个包含当前值的事件

提示：https://www.starknet.io/cairo-book/ch101-03-contract-events.html

## Step 5

使用 `sncast declare` 与 `sncast deploy` 将合约部署至 Sepolia 测试网

并使用 `sncast call` 与 `sncast invoke` 测试 `get` 和 `inc` 方法