---
title: "Метод IHostTaskManager::ReverseLeaveRuntime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.ReverseLeaveRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: db8a9114cd15a4e7d42e8f99941d4bcbb9faa842
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="7b7d9-102">Метод IHostTaskManager::ReverseLeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="7b7d9-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="7b7d9-103">Уведомляет основное приложение, что элемент управления оставляя общеязыковой среды выполнения (CLR) и неуправляемой функции, которая, в свою очередь, была вызвана из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b7d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b7d9-104">Syntax</span></span>  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7b7d9-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7b7d9-105">Return Value</span></span>  
  
|<span data-ttu-id="7b7d9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7b7d9-106">HRESULT</span></span>|<span data-ttu-id="7b7d9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7b7d9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b7d9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b7d9-108">S_OK</span></span>|<span data-ttu-id="7b7d9-109">`ReverseLeaveRuntime`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="7b7d9-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7b7d9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7b7d9-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7b7d9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7b7d9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7b7d9-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-113">The call timed out.</span></span>|  
|<span data-ttu-id="7b7d9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7b7d9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7b7d9-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7b7d9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7b7d9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7b7d9-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7b7d9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7b7d9-118">E_FAIL</span></span>|<span data-ttu-id="7b7d9-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7b7d9-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7b7d9-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7b7d9-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7b7d9-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7b7d9-123">Недостаточно памяти для выполнения запрашиваемого выделения ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b7d9-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b7d9-124">Remarks</span></span>  
 <span data-ttu-id="7b7d9-125">Среда CLR вызывает `ReverseLeaveRuntime` для оповещения о том, что текущая выполняющаяся задача возвращает узел элемента управления в неуправляемую функцию, которая в свою очередь, была вызвана из управляемого кода посредством вызова.</span><span class="sxs-lookup"><span data-stu-id="7b7d9-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="7b7d9-126">Каждый вызов `ReverseLeaveRuntime` совпадает с соответствующим вызовом [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="7b7d9-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b7d9-127">Требования</span><span class="sxs-lookup"><span data-stu-id="7b7d9-127">Requirements</span></span>  
 <span data-ttu-id="7b7d9-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b7d9-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b7d9-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7b7d9-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7b7d9-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b7d9-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b7d9-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b7d9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b7d9-132">См. также</span><span class="sxs-lookup"><span data-stu-id="7b7d9-132">See Also</span></span>  
 [<span data-ttu-id="7b7d9-133">CallNeedsHostHook-метод</span><span class="sxs-lookup"><span data-stu-id="7b7d9-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)  
 [<span data-ttu-id="7b7d9-134">EnterRuntime-метод</span><span class="sxs-lookup"><span data-stu-id="7b7d9-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)  
 [<span data-ttu-id="7b7d9-135">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="7b7d9-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="7b7d9-136">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="7b7d9-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="7b7d9-137">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="7b7d9-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="7b7d9-138">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="7b7d9-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="7b7d9-139">LeaveRuntime-метод</span><span class="sxs-lookup"><span data-stu-id="7b7d9-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)  
 [<span data-ttu-id="7b7d9-140">Подробный обзор вызова неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="7b7d9-140">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)