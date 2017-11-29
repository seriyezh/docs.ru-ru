---
title: "Метод ISymUnmanagedConstant::GetName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedConstant.GetName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4b6dc3eb79f351041687586327e4e095225acf4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="b3efb-102">Метод ISymUnmanagedConstant::GetName</span><span class="sxs-lookup"><span data-stu-id="b3efb-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="b3efb-103">Возвращает имя константы.</span><span class="sxs-lookup"><span data-stu-id="b3efb-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3efb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3efb-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3efb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3efb-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b3efb-106">[in] Длина буфера, `szName` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="b3efb-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b3efb-107">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, должны содержать имя, включая нулем.</span><span class="sxs-lookup"><span data-stu-id="b3efb-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="b3efb-108">[out] Буфер, в которой хранится имя.</span><span class="sxs-lookup"><span data-stu-id="b3efb-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3efb-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b3efb-109">Return Value</span></span>  
 <span data-ttu-id="b3efb-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b3efb-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3efb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b3efb-111">Requirements</span></span>  
 <span data-ttu-id="b3efb-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b3efb-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3efb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b3efb-113">See Also</span></span>  
 [<span data-ttu-id="b3efb-114">Isymunmanagedconstant-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b3efb-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="b3efb-115">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="b3efb-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)  
 [<span data-ttu-id="b3efb-116">GetValue-метод</span><span class="sxs-lookup"><span data-stu-id="b3efb-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)