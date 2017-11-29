---
title: "Метод ICorProfilerInfo2::GetGenerationBounds"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetGenerationBounds
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 33f1e130d214e28b8153b1aaf722c3df97edef37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="40b13-102">Метод ICorProfilerInfo2::GetGenerationBounds</span><span class="sxs-lookup"><span data-stu-id="40b13-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="40b13-103">Получает области памяти, которые являются сегментами кучи, составляющими разные поколения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="40b13-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40b13-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40b13-104">Syntax</span></span>  
  
```  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40b13-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="40b13-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="40b13-106">[in] Количество элементов, выделенных вызывающим объектом для массива `ranges`.</span><span class="sxs-lookup"><span data-stu-id="40b13-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="40b13-107">[out] Указатель на целое число, задающее общее число диапазонов, некоторые или все из которых будут возвращены в массиве `ranges`.</span><span class="sxs-lookup"><span data-stu-id="40b13-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="40b13-108">[out] Массив [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) структуры, каждый из которых описывает диапазон (блок) памяти в поколении, для которого выполняется сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="40b13-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40b13-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="40b13-109">Remarks</span></span>  
 <span data-ttu-id="40b13-110">Метод `GetGenerationBounds` Метод может быть вызван из любого обратного вызова профилировщика при условии, что в этот момент не выполняется сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="40b13-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="40b13-111">То есть, его можно вызывать из любого обратного вызова, за исключением тех, которые происходят между [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) и [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="40b13-111">That is, it can be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
 <span data-ttu-id="40b13-112">Большинство смещений поколений происходит во время сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="40b13-112">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="40b13-113">Поколения могут увеличиваться между сборками мусора, но обычно не перемещаются.</span><span class="sxs-lookup"><span data-stu-id="40b13-113">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="40b13-114">Таким образом, наиболее интересные места вызова метода `GetGenerationBounds` — `ICorProfilerCallback2::GarbageCollectionStarted` и `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="40b13-114">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="40b13-115">При запуске программы некоторые объекты выделяются самой средой (CLR), обычно в поколениях 3 и 0.</span><span class="sxs-lookup"><span data-stu-id="40b13-115">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="40b13-116">Таким образом, к моменту начала выполнения управляемого кода эти поколения уже будут содержать объекты.</span><span class="sxs-lookup"><span data-stu-id="40b13-116">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="40b13-117">Поколения 1 и 2 обычно оказываются пустыми, разве что кроме фиктивных объектов, созданных сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="40b13-117">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="40b13-118">(Размер фиктивных объектов составляет 12 байт в 32-разрядных реализациях среды CLR; в 64-разрядных реализациях размер больше). Вы также можете видеть диапазоны поколения 2, которые находятся внутри модулей, созданных генератором образов в машинном коде (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="40b13-118">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="40b13-119">В этом случае объекты в поколении 2 являются *замороженными объектами*, которые выделяются при выполнении NGen.exe, а не при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="40b13-119">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="40b13-120">Эта функция использует буферы, выделенные вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="40b13-120">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40b13-121">Требования</span><span class="sxs-lookup"><span data-stu-id="40b13-121">Requirements</span></span>  
 <span data-ttu-id="40b13-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40b13-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40b13-123">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40b13-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40b13-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40b13-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40b13-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40b13-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b13-126">См. также</span><span class="sxs-lookup"><span data-stu-id="40b13-126">See Also</span></span>  
 [<span data-ttu-id="40b13-127">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="40b13-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="40b13-128">ICorProfilerInfo2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="40b13-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="40b13-129">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="40b13-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="40b13-130">Профилирование</span><span class="sxs-lookup"><span data-stu-id="40b13-130">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)