# ax_classification_python_vs_cpp


## ax-samples(C++)
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

## axPyEngine

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
