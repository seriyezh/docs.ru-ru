---
title: "Метод IMetaDataImport::EnumMethodSemantics"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethodSemantics
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0d5ec79701f73b8beb7759d72b972fc347a339c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="5b06b-102">Метод IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="5b06b-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="5b06b-103">Перечисляет свойства и события их изменения, с которыми связан указанный метод.</span><span class="sxs-lookup"><span data-stu-id="5b06b-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b06b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b06b-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b06b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b06b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5b06b-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="5b06b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5b06b-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="5b06b-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="5b06b-108">[in] Токен MethodDef, который ограничивает область перечисления.</span><span class="sxs-lookup"><span data-stu-id="5b06b-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="5b06b-109">[out] Массив, используемый для хранения события или свойства.</span><span class="sxs-lookup"><span data-stu-id="5b06b-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5b06b-110">[in] Максимальный размер массива `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="5b06b-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="5b06b-111">[out] Количество событий или свойств, возвращаемых в `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="5b06b-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b06b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5b06b-112">Return Value</span></span>  
  
|<span data-ttu-id="5b06b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b06b-113">HRESULT</span></span>|<span data-ttu-id="5b06b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5b06b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5b06b-115">`EnumMethodSemantics`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5b06b-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5b06b-116">Отсутствуют события и свойства для перечисления.</span><span class="sxs-lookup"><span data-stu-id="5b06b-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="5b06b-117">В этом случае `pcEventProp` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="5b06b-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b06b-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b06b-118">Remarks</span></span>  
 <span data-ttu-id="5b06b-119">Определение много типами среды CLR *свойство* `Changed` событий и `On` *свойство* `Changed` методы, относящиеся к их свойствам.</span><span class="sxs-lookup"><span data-stu-id="5b06b-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="5b06b-120">Например <xref:System.Windows.Forms.Control?displayProperty=nameWithType> определяет тип <xref:System.Windows.Forms.Control.Font%2A> свойства <xref:System.Windows.Forms.Control.FontChanged> события и <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="5b06b-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="5b06b-121">Метод доступа set <xref:System.Windows.Forms.Control.Font%2A> вызовы свойство <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод, который в свою очередь вызывает <xref:System.Windows.Forms.Control.FontChanged> событий.</span><span class="sxs-lookup"><span data-stu-id="5b06b-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="5b06b-122">Вызовите `EnumMethodSemantics` с помощью MethodDef для <xref:System.Windows.Forms.Control.OnFontChanged%2A> для получения ссылок на <xref:System.Windows.Forms.Control.Font%2A> свойство и <xref:System.Windows.Forms.Control.FontChanged> событий.</span><span class="sxs-lookup"><span data-stu-id="5b06b-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b06b-123">Требования</span><span class="sxs-lookup"><span data-stu-id="5b06b-123">Requirements</span></span>  
 <span data-ttu-id="5b06b-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b06b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b06b-125">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5b06b-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b06b-126">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b06b-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b06b-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b06b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b06b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5b06b-128">See Also</span></span>  
 [<span data-ttu-id="5b06b-129">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5b06b-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="5b06b-130">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5b06b-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)