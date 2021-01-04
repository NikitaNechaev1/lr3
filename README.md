# lr3
Лабораторная работа #3<br />
Методы аугментации данных<br />
Цель лабораторной работы : Добавить методы аугментации данных в цикл обучения
сверточной нейронной сети для восстановления информации в цветовых каналах
изображения
Задачи:<br />
1. Используя окружение для обучения нейронной сети из лабораторной работы #2
выполнить:<br />
""" при выполнении пунктов 1а-1d картинки были подготовлены используя 1 tf-record на 1 картинку. По этой причине на 5 - 12 эпохе заполнялась оперативная память. На количестве картинок ~60 000 эта проблема была решена путём увеличения числа картинок в одном tf-record файле (уменьшения числа shards). Train - 5000 кадров фильмов "Шестиструнный самурай" и "Ничего хорошего в отеле Эль Рояль", validation - 500 фотографий из личного архива """<br />
    a. Обучить нейронную сеть с использованием метода аугментации ‘случайная
часть изображения’<br />
Аугментация:<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_1.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_2.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_3.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_4.png)<br />
Результат обучения:<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_results_graph.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_crop_results_image.png)
    b. Обучить нейронную сеть с использованием метода аугментации ‘случайное
горизонтальное отражение’<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/random_flip_1.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/random_flip_2.png)<br />
Результат обучения:<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_flip_results_graph.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_flip_results_image.png)<br />
    c. Обучить нейронную сеть с использованием метода аугментации ‘поворот на
случайный угол’<br />
Аугментация:<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/random_rot_1.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/random_rot_2.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/random_rot_3.png)<br />
Результат обучения:<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_rot_results_graph.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_rot_results_image.png)<br />
    d. Обучить нейронную сеть используя методы аугментации a-с<br />
 Аугментация:<br />
 ![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/all_augm_1.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/all_augm_2.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/all_augm_3.png)<br />
Результат обучения:<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/lr3_5000_graphs.png)
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/randm_flip_crop_rot_results_image.png)<br />
<br />
     
2. Подготовить набор данных из минимум 50000 изображений и повторить на нем
пункт 1.d<br />
Train - 63 520 кадров фильмов "Шестиструнный самурай" и "Ничего хорошего в отеле Эль Рояль", validation - 852 фотографий из личного архива """<br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/63k_images_results.png)<br />
Было подозрение на переобучение из-за того, что в фильме много кадров друг на друга похожи и там нет фотографии наподобии тех, которые в validation. Поэтому предпинята попытка обучения на 67 117 фотографий случайно взятых из соцсетей https://www.kaggle.com/greg115/various-tagged-images 
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/67k_images_results.png)<br />
График обучения: <br />
![alt text](https://github.com/NikitaNechaev1/lr3/blob/main/lr3-results/67k_63k_images_results_graphs.png)<br />
<br />
Пример лога:
2021-01-03 17:51:48.723206: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cudart64_110.dll
2021-01-03 17:51:50.743630: I tensorflow/core/platform/cpu_feature_guard.cc:142] This TensorFlow binary is optimized with oneAPI Deep Neural Network Library (oneDNN) to use the follow
ing CPU instructions in performance-critical operations:  AVX2
To enable them in other operations, rebuild TensorFlow with the appropriate compiler flags.
2021-01-03 17:51:50.769263: I tensorflow/compiler/xla/service/service.cc:168] XLA service 0x20c9e938f20 initialized for platform Host (this does not guarantee that XLA will be used).
Devices:
2021-01-03 17:51:50.772546: I tensorflow/compiler/xla/service/service.cc:176]   StreamExecutor device (0): Host, Default Version
2021-01-03 17:51:50.775560: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library nvcuda.dll
2021-01-03 17:51:50.817898: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1720] Found device 0 with properties:
pciBusID: 0000:07:00.0 name: GeForce RTX 2070 computeCapability: 7.5
coreClock: 1.83GHz coreCount: 36 deviceMemorySize: 8.00GiB deviceMemoryBandwidth: 417.29GiB/s
2021-01-03 17:51:50.822564: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cudart64_110.dll
2021-01-03 17:51:50.829203: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cublas64_11.dll
2021-01-03 17:51:50.831563: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cublasLt64_11.dll
2021-01-03 17:51:50.836204: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cufft64_10.dll
2021-01-03 17:51:50.839391: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library curand64_10.dll
2021-01-03 17:51:50.846632: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cusolver64_10.dll
2021-01-03 17:51:50.850422: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cusparse64_11.dll
2021-01-03 17:51:50.853440: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cudnn64_8.dll
2021-01-03 17:51:50.855827: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1862] Adding visible gpu devices: 0
2021-01-03 17:51:51.405225: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1261] Device interconnect StreamExecutor with strength 1 edge matrix:
2021-01-03 17:51:51.407899: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1267]      0
2021-01-03 17:51:51.409632: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1280] 0:   N
2021-01-03 17:51:51.411827: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1406] Created TensorFlow device (/job:localhost/replica:0/task:0/device:GPU:0 with 6553 MB memory) -> ph
ysical GPU (device: 0, name: GeForce RTX 2070, pci bus id: 0000:07:00.0, compute capability: 7.5)
2021-01-03 17:51:51.422196: I tensorflow/compiler/xla/service/service.cc:168] XLA service 0x20cca3f9d20 initialized for platform CUDA (this does not guarantee that XLA will be used).
Devices:
2021-01-03 17:51:51.425707: I tensorflow/compiler/xla/service/service.cc:176]   StreamExecutor device (0): GeForce RTX 2070, Compute Capability 7.5
WARNING:tensorflow:From E:/Nicky/soroka_lab/train-by-chunks.py:41: The name tf.keras.backend.set_session is deprecated. Please use tf.compat.v1.keras.backend.set_session instead.

2021-01-03 17:51:51.429680: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1720] Found device 0 with properties:
pciBusID: 0000:07:00.0 name: GeForce RTX 2070 computeCapability: 7.5
coreClock: 1.83GHz coreCount: 36 deviceMemorySize: 8.00GiB deviceMemoryBandwidth: 417.29GiB/s
2021-01-03 17:51:51.435646: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cudart64_110.dll
2021-01-03 17:51:51.438202: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cublas64_11.dll
2021-01-03 17:51:51.441026: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cublasLt64_11.dll
2021-01-03 17:51:51.443453: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cufft64_10.dll
2021-01-03 17:51:51.445868: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library curand64_10.dll
2021-01-03 17:51:51.448255: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cusolver64_10.dll
2021-01-03 17:51:51.450906: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cusparse64_11.dll
2021-01-03 17:51:51.453405: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cudnn64_8.dll
2021-01-03 17:51:51.455930: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1862] Adding visible gpu devices: 0
2021-01-03 17:51:51.458691: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1720] Found device 0 with properties:
pciBusID: 0000:07:00.0 name: GeForce RTX 2070 computeCapability: 7.5
coreClock: 1.83GHz coreCount: 36 deviceMemorySize: 8.00GiB deviceMemoryBandwidth: 417.29GiB/s
2021-01-03 17:51:51.463570: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cudart64_110.dll
2021-01-03 17:51:51.466105: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cublas64_11.dll
2021-01-03 17:51:51.469448: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cublasLt64_11.dll
2021-01-03 17:51:51.471907: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cufft64_10.dll
2021-01-03 17:51:51.474308: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library curand64_10.dll
2021-01-03 17:51:51.477088: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cusolver64_10.dll
2021-01-03 17:51:51.478982: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cusparse64_11.dll
2021-01-03 17:51:51.480924: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cudnn64_8.dll
2021-01-03 17:51:51.483689: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1862] Adding visible gpu devices: 0
2021-01-03 17:51:51.485920: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1261] Device interconnect StreamExecutor with strength 1 edge matrix:
2021-01-03 17:51:51.487851: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1267]      0
2021-01-03 17:51:51.489493: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1280] 0:   N
2021-01-03 17:51:51.491267: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1406] Created TensorFlow device (/job:localhost/replica:0/task:0/device:GPU:0 with 6553 MB memory) -> ph
ysical GPU (device: 0, name: GeForce RTX 2070, pci bus id: 0000:07:00.0, compute capability: 7.5)
2021-01-03 17:51:51.623455: I tensorflow/compiler/mlir/mlir_graph_optimization_pass.cc:116] None of the MLIR optimization passes are enabled (registered 2)
Count of train images: 63520
Count of validation images: 852
2021-01-03 17:52:46.489799: I tensorflow/core/profiler/lib/profiler_session.cc:136] Profiler session initializing.
2021-01-03 17:52:46.491787: I tensorflow/core/profiler/lib/profiler_session.cc:155] Profiler session started.
2021-01-03 17:52:46.494253: I tensorflow/core/profiler/internal/gpu/cupti_tracer.cc:1365] Profiler found 1 GPUs
2021-01-03 17:52:46.503358: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cupti64_110.dll
2021-01-03 17:52:46.579942: I tensorflow/core/profiler/lib/profiler_session.cc:172] Profiler session tear down.
2021-01-03 17:52:46.582098: I tensorflow/core/profiler/internal/gpu/cupti_tracer.cc:1487] CUPTI activity buffer flushed
Epoch 1/5
2021-01-03 17:52:47.904122: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cudnn64_8.dll
2021-01-03 17:52:50.362457: I tensorflow/core/platform/windows/subprocess.cc:308] SubProcess ended with return code: 0

2021-01-03 17:52:50.415549: I tensorflow/core/platform/windows/subprocess.cc:308] SubProcess ended with return code: 0

2021-01-03 17:52:50.479886: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cublas64_11.dll
2021-01-03 17:52:51.277033: I tensorflow/stream_executor/platform/default/dso_loader.cc:49] Successfully opened dynamic library cublasLt64_11.dll
      1/Unknown - 6s 6s/step - loss: 0.14852021-01-03 17:52:52.843614: I tensorflow/core/profiler/lib/profiler_session.cc:136] Profiler session initializing.
2021-01-03 17:52:52.845994: I tensorflow/core/profiler/lib/profiler_session.cc:155] Profiler session started.
      2/Unknown - 8s 2s/step - loss: 0.14232021-01-03 17:52:54.527344: I tensorflow/core/profiler/lib/profiler_session.cc:71] Profiler session collecting data.
2021-01-03 17:52:54.531740: I tensorflow/core/profiler/internal/gpu/cupti_tracer.cc:1487] CUPTI activity buffer flushed
2021-01-03 17:52:54.735042: I tensorflow/core/profiler/internal/gpu/cupti_collector.cc:228]  GpuTracer has collected 3903 callback api events and 3573 activity events.
2021-01-03 17:52:54.781127: I tensorflow/core/profiler/lib/profiler_session.cc:172] Profiler session tear down.
2021-01-03 17:52:54.889402: I tensorflow/core/profiler/rpc/client/save_profile.cc:137] Creating directory: E:\Nicky\soroka_lab/log_lab3/20210103-175151\train\plugins\profile\2021_01_0
3_14_52_54
2021-01-03 17:52:54.952186: I tensorflow/core/profiler/rpc/client/save_profile.cc:143] Dumped gzipped tool data for trace.json.gz to E:\Nicky\soroka_lab/log_lab3/20210103-175151\train
\plugins\profile\2021_01_03_14_52_54\DESKTOP-67BS2ML.trace.json.gz
2021-01-03 17:52:55.016142: I tensorflow/core/profiler/rpc/client/save_profile.cc:137] Creating directory: E:\Nicky\soroka_lab/log_lab3/20210103-175151\train\plugins\profile\2021_01_0
3_14_52_54
2021-01-03 17:52:55.044719: I tensorflow/core/profiler/rpc/client/save_profile.cc:143] Dumped gzipped tool data for memory_profile.json.gz to E:\Nicky\soroka_lab/log_lab3/20210103-175
151\train\plugins\profile\2021_01_03_14_52_54\DESKTOP-67BS2ML.memory_profile.json.gz
2021-01-03 17:52:55.176994: I tensorflow/core/profiler/rpc/client/capture_profile.cc:251] Creating directory: E:\Nicky\soroka_lab/log_lab3/20210103-175151\train\plugins\profile\2021_0
1_03_14_52_54Dumped tool data for xplane.pb to E:\Nicky\soroka_lab/log_lab3/20210103-175151\train\plugins\profile\2021_01_03_14_52_54\DESKTOP-67BS2ML.xplane.pb
Dumped tool data for overview_page.pb to E:\Nicky\soroka_lab/log_lab3/20210103-175151\train\plugins\profile\2021_01_03_14_52_54\DESKTOP-67BS2ML.overview_page.pb
Dumped tool data for input_pipeline.pb to E:\Nicky\soroka_lab/log_lab3/20210103-175151\train\plugins\profile\2021_01_03_14_52_54\DESKTOP-67BS2ML.input_pipeline.pb
Dumped tool data for tensorflow_stats.pb to E:\Nicky\soroka_lab/log_lab3/20210103-175151\train\plugins\profile\2021_01_03_14_52_54\DESKTOP-67BS2ML.tensorflow_stats.pb
Dumped tool data for kernel_stats.pb to E:\Nicky\soroka_lab/log_lab3/20210103-175151\train\plugins\profile\2021_01_03_14_52_54\DESKTOP-67BS2ML.kernel_stats.pb

1000/1000 [==============================] - 383s 378ms/step - loss: 0.0447 - val_loss: 0.1336
Epoch 2/5
1000/1000 [==============================] - 361s 361ms/step - loss: 0.0420 - val_loss: 0.1353
Epoch 3/5
1000/1000 [==============================] - 334s 334ms/step - loss: 0.0419 - val_loss: 0.1298
Epoch 4/5
1000/1000 [==============================] - 336s 336ms/step - loss: 0.0409 - val_loss: 0.1281
Epoch 5/5
1000/1000 [==============================] - 336s 336ms/step - loss: 0.0413 - val_loss: 0.1350
Model: "sequential"
_________________________________________________________________
Layer (type)                 Output Shape              Param #
=================================================================
conv2d (Conv2D)              (None, 224, 224, 1)       10
_________________________________________________________________
conv2d_1 (Conv2D)            (None, 112, 112, 32)      320
_________________________________________________________________
conv2d_2 (Conv2D)            (None, 56, 56, 64)        18496
_________________________________________________________________
conv2d_3 (Conv2D)            (None, 28, 28, 128)       73856
_________________________________________________________________
conv2d_transpose (Conv2DTran (None, 56, 56, 128)       147584
_________________________________________________________________
conv2d_transpose_1 (Conv2DTr (None, 112, 112, 64)      73792
_________________________________________________________________
conv2d_transpose_2 (Conv2DTr (None, 224, 224, 2)       1154
=================================================================
Total params: 315,212
Trainable params: 315,212
Non-trainable params: 0
_________________________________________________________________
None

