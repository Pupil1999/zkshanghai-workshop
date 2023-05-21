# 第2课 课后作业

## 第1题 Num2Bits
<pre><code>pragma circom 2.1.4;

template Num2Bits(nBits) {
    signal input in;
    signal output b[nBits];
    var check = 0;

    for(var i = 0; i < nBits; i++){
        b[i] <-- (in >> i) & 1;
        check += b[i] * 2**i;
        b[i] * (b[i] - 1) === 0;
    }
    
    in === check;
}

component main = Num2Bits(4);

/* INPUT = {
    "in": 12
} */
</code></pre>

## 第2题 
