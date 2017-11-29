---
title: "Перечисление CorDebugUserState"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugUserState
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugUserState
helpviewer_keywords: CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 95240dfea92a4ebbf2c7b9c11b7376d912c40fe5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="8a372-102">Перечисление CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="8a372-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="8a372-103">Указывает состояние пользователя потока.</span><span class="sxs-lookup"><span data-stu-id="8a372-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a372-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a372-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a><span data-ttu-id="8a372-105">Члены</span><span class="sxs-lookup"><span data-stu-id="8a372-105">Members</span></span>  
  
|<span data-ttu-id="8a372-106">Значение</span><span class="sxs-lookup"><span data-stu-id="8a372-106">Value</span></span>|<span data-ttu-id="8a372-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8a372-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="8a372-108">Запрошено завершение выполнения потока.</span><span class="sxs-lookup"><span data-stu-id="8a372-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="8a372-109">Приостановка потока был запрошен.</span><span class="sxs-lookup"><span data-stu-id="8a372-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="8a372-110">Поток выполняется в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="8a372-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="8a372-111">Поток не запущен выполнения.</span><span class="sxs-lookup"><span data-stu-id="8a372-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="8a372-112">Поток был завершен.</span><span class="sxs-lookup"><span data-stu-id="8a372-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="8a372-113">Поток ожидает другого потока до завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="8a372-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="8a372-114">Этот поток был приостановлен.</span><span class="sxs-lookup"><span data-stu-id="8a372-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="8a372-115">Поток находится в небезопасной точке.</span><span class="sxs-lookup"><span data-stu-id="8a372-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="8a372-116">То есть поток находится в точке выполнения, в которой он может блокировать сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="8a372-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="8a372-117">Отладка событий могут доставляться в небезопасных точках, но приостановка потока в небезопасной точке вероятнее всего вызовет взаимоблокировку до возобновления потока.</span><span class="sxs-lookup"><span data-stu-id="8a372-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="8a372-118">Безопасные и небезопасные точки определяются just-in-time (JIT) и реализацию сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="8a372-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="8a372-119">Поток находится в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="8a372-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a372-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a372-120">Remarks</span></span>  
 <span data-ttu-id="8a372-121">Пользовательское состояние потока — используется состояние потока при его анализа отладчиком.</span><span class="sxs-lookup"><span data-stu-id="8a372-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="8a372-122">Для потока может быть сочетание пользовательских состояний.</span><span class="sxs-lookup"><span data-stu-id="8a372-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="8a372-123">Используйте [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) метод, чтобы получить состояние пользователя потока.</span><span class="sxs-lookup"><span data-stu-id="8a372-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a372-124">Требования</span><span class="sxs-lookup"><span data-stu-id="8a372-124">Requirements</span></span>  
 <span data-ttu-id="8a372-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a372-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a372-126">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a372-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a372-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a372-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a372-128">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a372-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a372-129">См. также</span><span class="sxs-lookup"><span data-stu-id="8a372-129">See Also</span></span>  
 [<span data-ttu-id="8a372-130">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="8a372-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)