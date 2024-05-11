# 8BIT_SYNCHRONOUS_UP-DOWN_COUNTER
![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/e1af47bf-e77f-446e-9fe0-e0ca3d1a7cfd)
# Here is a diagram showing the circuit in the "up" counting mode
![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/8a6dd34b-5226-4d93-9bff-d87ab85aeabc)
# Here, shown in the "down" counting mode
![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/9a30ebd6-6692-48d0-b64b-41b896d6de4a)
# PROGRAM
```
module ripple_carry_counter(q, clk, reset);
output [3:0] q;
input clk, reset;
T_FF tff0(q[0], clk, reset);
T_FF tff1(q[1], q[0], reset);
T_FF tff2(q[2], q[1], reset);
T_FF tff3(q[3], q[2], reset);
endmodule
module T_FF(q, clk, reset);
output q;
input clk, reset;
wire d;
D_FF dff0(q, d, clk, reset);
not n1(d, q);
endmodule
module D_FF(q, d, clk, reset);
output q;
input d, clk, reset;
reg q;
always @(posedge reset or negedge clk)
if (reset)
q = 1'b0;
else
q = d;
endmodule
```

# OUTPUT
![image](https://github.com/Vijayananthperumal22/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/107705127/ce5ac5ca-c0df-4700-b80b-e2ec1c50d95e)

