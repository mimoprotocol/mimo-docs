# mimo automator

## Basic Functions
### function to convert a timestamp to 32 bytes hex
```
function deadline() {
  ts=`date +"%s"`
  printf "%064x\n" `expr $ts + 60`
}
```

### function to convert a decimal number to 32 bytes hex
```
function decimal2hex() {
  echo "ibase=A;obase=16;$1" | bc | xargs -0 -I h printf "%64s" h | sed "s/ /0/g"
}
```

## Construct `ioctl` Commands
### Add liquidity
```
function addLiquidity() {
  exchange=$1
  min_liquidity=`decimal2hex $2`
  max_tokens=`decimal2hex $3`
  iotx_amount=$4
  dl=`deadline`
  ioctl contract invoke bytecode $exchange 422f1043${min_liquidity}${max_tokens}${dl}
}
```

### Remove liquidity
```
function removeLiquidity() {
  exchange=$1
  amount=`decimal2hex $2`
  min_iotx=`decimal2hex $3`
  min_tokens=`decimal2hex $4`
  dl=`deadline`
  ioctl contract invoke bytecode $exchange f88bf15a${amount}${min_iotx}${min_tokens}${dl}
}
```

### Get token to IOTX input price
```
function getTokenToIotxInputPrice() {
  exchange=$1
  amount=`decimal2hex $2`
  ioctl action read $exchange d458a2d1${amount}
}
```

### Get IOTX to token input price
```
function getIotxToTokenInputPrice() {
  exchange=$1
  amount=`decimal2hex $2`
  ioctl action read $exchange a46f9389${amount}
}
```

### Swap token to IOTX
```
function tokenToIotxSwapInput() {
  exchange=$1
  token_sold=`decimal2hex $2`
  min_iotx=`decimal2hex $3`
  dl=`deadline`
  ioctl contract invoke bytecode $exchange 10dc202f${token_sold}${min_iotx}${dl}
}
```

### Swap IOTX to token
```
function iotxToTokenSwapInput() {
  exchange=$1
  iotx_sold=`decimal2hex $2`
  min_token=`decimal2hex $3`
  dl=`deadline`
  ioctl contract invoke bytecode $exchange eecd096a${iotx_sold}${min_token}${dl}
}
```

