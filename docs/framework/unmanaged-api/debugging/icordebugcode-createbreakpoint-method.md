---
title: "Метод ICorDebugCode::CreateBreakpoint"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.CreateBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 214d032129613230b8c55cdd286ea637227a626e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="6bb22-102">Метод ICorDebugCode::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6bb22-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="6bb22-103">Создает точку останова в этом сегменте кода с указанным смещением.</span><span class="sxs-lookup"><span data-stu-id="6bb22-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bb22-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6bb22-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bb22-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6bb22-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="6bb22-106">[in] Позиция, с которого нужно создать точку останова.</span><span class="sxs-lookup"><span data-stu-id="6bb22-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="6bb22-107">[out] Указатель на адрес объекта «ICorDebugFunctionBreakpoint», который представляет точку останова.</span><span class="sxs-lookup"><span data-stu-id="6bb22-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bb22-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6bb22-108">Remarks</span></span>  
 <span data-ttu-id="6bb22-109">Перед активна, его необходимо добавить в объект процесса.</span><span class="sxs-lookup"><span data-stu-id="6bb22-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="6bb22-110">Если данный пример кода является код на промежуточном языке (MSIL), и нет just-in-time (JIT)-компиляции, машинная версия кода, точка останова будет применяться в JIT-скомпилированном коде.</span><span class="sxs-lookup"><span data-stu-id="6bb22-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="6bb22-111">(То же самое значение true, если код является JIT-компиляции более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="6bb22-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bb22-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6bb22-112">Requirements</span></span>  
 <span data-ttu-id="6bb22-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bb22-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bb22-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bb22-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bb22-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bb22-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bb22-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bb22-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb22-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6bb22-117">See Also</span></span>  
 