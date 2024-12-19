# ax_classification_python_vs_cpp

## ABST
Module-LLM(ax630)にて、PyAXEngine(Python)で1回目の推論の実行時間が遅いので、C++と比較した。

https://x.com/nnn112358/status/1869695184994480277


## ax-samples(C++) mobilenetv2
```
root@m5stack-LLM:/opt/usr/241219_test# ./ax_classification -m mobilenetv2.axmodel -i cat.jpg -r 10
--------------------------------------
model file : mobilenetv2.axmodel
image file : cat.jpg
img_h, img_w : 224 224
--------------------------------------
Engine creating handle is done.
Engine creating context is done.
Engine get io info is done.
Engine alloc io is done.
Engine push input is done.
--------------------------------------
topk cost time:0.15 ms
9.5770, 285
9.4225, 283
9.2681, 282
8.9591, 281
7.7234, 279
--------------------------------------
time_costs[0]: 1.00 ms
time_costs[1]: 0.85 ms
time_costs[2]: 0.82 ms
time_costs[3]: 0.82 ms
time_costs[4]: 0.82 ms
time_costs[5]: 0.82 ms
time_costs[6]: 0.82 ms
time_costs[7]: 0.82 ms
time_costs[8]: 0.82 ms
time_costs[9]: 0.82 ms
Repeat 10 times, avg time 0.84 ms, max_time 1.00 ms, min_time 0.82 ms
```

## axPyEngine mobilenetv2

```
root@m5stack-LLM:/opt/usr/241219_test# python3 classification.py
[INFO] Chip type: ChipType.MC20E
[INFO] Engine version: 2.6.3sp
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Model type: 1 (full core)
[INFO] Compiler version: 3.2-patch1 0a2535b6
Trial 1: time: 30.32 ms
Trial 2: time: 1.54 ms
Trial 3: time: 1.52 ms
Trial 4: time: 1.56 ms
Trial 5: time: 1.66 ms
Trial 6: time: 1.54 ms
Trial 7: time: 1.63 ms
Trial 8: time: 1.52 ms
Trial 9: time: 1.52 ms
Trial 10: time: 1.51 ms
Top 5 Predictions:
Class Index: 282, Score: 9.731452941894531
Class Index: 281, Score: 8.341245651245117
Class Index: 285, Score: 7.72337532043457
Class Index: 278, Score: 7.72337532043457
Class Index: 356, Score: 7.414440155029297
```
## ax-samples(C++) swin-tiny

```
root@m5stack-LLM:/opt/usr/241219_test# ./ax_classification -m swin-tiny-patch4-window7-224_sim.axmodel -i cat.jpg -r 10
--------------------------------------
model file : swin-tiny-patch4-window7-224_sim.axmodel
image file : cat.jpg
img_h, img_w : 224 224
--------------------------------------
Engine creating handle is done.
Engine creating context is done.
Engine get io info is done.
Engine alloc io is done.
Engine push input is done.
--------------------------------------
topk cost time:0.09 ms
3.5129, 285
3.1226, 282
2.5371, 281
2.4070, 356
2.3419, 279
--------------------------------------
time_costs[0]: 18.60 ms
time_costs[1]: 18.46 ms
time_costs[2]: 18.43 ms
time_costs[3]: 18.45 ms
time_costs[4]: 18.44 ms
time_costs[5]: 18.43 ms
time_costs[6]: 18.43 ms
time_costs[7]: 18.44 ms
time_costs[8]: 18.43 ms
time_costs[9]: 18.43 ms
Repeat 10 times, avg time 18.45 ms, max_time 18.60 ms, min_time 18.43 ms
```

## axPyEngine swin-tiny

```
root@m5stack-LLM:/opt/usr/241219_test# python3 classification.py
[INFO] Chip type: ChipType.MC20E
[INFO] Engine version: 2.6.3sp
[INFO] VNPU type: VNPUType.DISABLED
[INFO] Model type: 0 (half core)
[INFO] Compiler version: 3.3 3cdead5e
Trial 1: time: 45.25 ms
Trial 2: time: 19.15 ms
Trial 3: time: 19.22 ms
Trial 4: time: 19.14 ms
Trial 5: time: 19.16 ms
Trial 6: time: 19.32 ms
Trial 7: time: 19.17 ms
Trial 8: time: 19.14 ms
Trial 9: time: 19.16 ms
Trial 10: time: 19.18 ms
Top 5 Predictions:
Class Index: 285, Score: 4.228509426116943
Class Index: 281, Score: 3.447861671447754
Class Index: 282, Score: 3.317753791809082
Class Index: 331, Score: 2.992483615875244
Class Index: 283, Score: 2.6021599769592285
```
