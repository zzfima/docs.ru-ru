---
title: "Метод IMetaDataEmit::GetSaveSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.GetSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9686e8e2c4e8276e725852cb58fac7ed1973778b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="e9350-102">Метод IMetaDataEmit::GetSaveSize</span><span class="sxs-lookup"><span data-stu-id="e9350-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="e9350-103">Получает приблизительный двоичный размер сборки и ее метаданные в текущей области.</span><span class="sxs-lookup"><span data-stu-id="e9350-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9350-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9350-104">Syntax</span></span>  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9350-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9350-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="e9350-106">[in] Значение [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) перечисления, которое указывает, следует ли получить точное или приблизительное размер.</span><span class="sxs-lookup"><span data-stu-id="e9350-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="e9350-107">Допустимы только три значения: cssAccurate cssQuick и cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="e9350-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
-   <span data-ttu-id="e9350-108">cssAccurate возвращает точный размер сохранения, но занимает больше времени для вычисления.</span><span class="sxs-lookup"><span data-stu-id="e9350-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
-   <span data-ttu-id="e9350-109">cssQuick возвращает размер, для безопасности, но занимает меньше времени для вычисления.</span><span class="sxs-lookup"><span data-stu-id="e9350-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
-   <span data-ttu-id="e9350-110">сообщает cssDiscardTransientCAs `GetSaveSize` , он может отбрасывание удаляемое настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e9350-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="e9350-111">[out] Указатель на размер, необходимый для сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="e9350-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9350-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9350-112">Remarks</span></span>  
 <span data-ttu-id="e9350-113">`GetSaveSize`вычисляет размер, в байтах для сохранения сборки и ее метаданные в текущей области.</span><span class="sxs-lookup"><span data-stu-id="e9350-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="e9350-114">(Вызов [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) метод выдаст это число байтов.)</span><span class="sxs-lookup"><span data-stu-id="e9350-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="e9350-115">Если вызывающий объект реализует интерфейс [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) интерфейса (через [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) или [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` выполняет два прохода через метаданные для оптимизации, а затем сжать.</span><span class="sxs-lookup"><span data-stu-id="e9350-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="e9350-116">В противном случае оптимизация не выполняется.</span><span class="sxs-lookup"><span data-stu-id="e9350-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="e9350-117">Если выполнить оптимизацию, первый проход просто сортирует структуры метаданных для настройки производительности поиска во время импорта.</span><span class="sxs-lookup"><span data-stu-id="e9350-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="e9350-118">Этот шаг обычно приводит к перемещению записей относительно с побочным эффектом недействительными маркеров, сохраненных с помощью средства для дальнейшего использования.</span><span class="sxs-lookup"><span data-stu-id="e9350-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="e9350-119">Метаданные не информирования вызывающего объекта об этих изменениях маркера до выполнения второй передачи, однако.</span><span class="sxs-lookup"><span data-stu-id="e9350-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="e9350-120">При втором проходе выполняются различные оптимизации, предназначенные для снижения общего объема метаданных, например оптимизация (раннее связывание) `mdTypeRef` и `mdMemberRef` маркеры, если ссылка указывает на тип или член, объявленный в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="e9350-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="e9350-121">На этом этапе происходит другой цикл сопоставления маркеров.</span><span class="sxs-lookup"><span data-stu-id="e9350-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="e9350-122">После этого этапа ядро метаданных уведомляет о вызывающем объекте, через его `IMapToken` интерфейс какой-либо изменить значения маркера.</span><span class="sxs-lookup"><span data-stu-id="e9350-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9350-123">Требования</span><span class="sxs-lookup"><span data-stu-id="e9350-123">Requirements</span></span>  
 <span data-ttu-id="e9350-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9350-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9350-125">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e9350-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9350-126">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9350-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9350-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9350-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9350-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e9350-128">See Also</span></span>  
 [<span data-ttu-id="e9350-129">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e9350-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="e9350-130">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e9350-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
