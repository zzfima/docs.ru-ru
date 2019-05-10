---
title: Метод IMetaDataEmit::GetSaveSize
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21f6c07976198416bff6e8e2a1789e4ccbf5ca55
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665014"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="c0b36-102">Метод IMetaDataEmit::GetSaveSize</span><span class="sxs-lookup"><span data-stu-id="c0b36-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="c0b36-103">Получает приблизительный двоичный размер сборки и ее метаданные в текущей области.</span><span class="sxs-lookup"><span data-stu-id="c0b36-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0b36-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0b36-104">Syntax</span></span>  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0b36-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0b36-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="c0b36-106">[in] Значение [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) перечисление, указывающее, следует ли получить точное или приблизительное размер.</span><span class="sxs-lookup"><span data-stu-id="c0b36-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="c0b36-107">Допустимы только три значения: cssAccurate, cssQuick и cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="c0b36-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
- <span data-ttu-id="c0b36-108">cssAccurate возвращает точный размер сохранения, но требует больше времени для вычисления.</span><span class="sxs-lookup"><span data-stu-id="c0b36-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
- <span data-ttu-id="c0b36-109">cssQuick возвращает размер в целях безопасности, но занимает меньше времени, для которого требуется вычислить.</span><span class="sxs-lookup"><span data-stu-id="c0b36-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
- <span data-ttu-id="c0b36-110">сообщает cssDiscardTransientCAs `GetSaveSize` , может возникнуть исключение сейчас присваиваются значения настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="c0b36-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="c0b36-111">[out] Указатель на размер, необходимый для сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="c0b36-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0b36-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="c0b36-112">Remarks</span></span>  
 <span data-ttu-id="c0b36-113">`GetSaveSize` вычисляет размер, в байтах, чтобы сохранить сборку и все метаданные в текущей области.</span><span class="sxs-lookup"><span data-stu-id="c0b36-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="c0b36-114">(Вызов [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) метод выдаст это число байтов.)</span><span class="sxs-lookup"><span data-stu-id="c0b36-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="c0b36-115">Если вызывающий объект реализует [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) интерфейса (через [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) или [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` выполняет два прохода по метаданным для оптимизации и сжатия.</span><span class="sxs-lookup"><span data-stu-id="c0b36-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="c0b36-116">В противном случае оптимизация не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c0b36-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="c0b36-117">Если выполнить оптимизацию, первый проход просто сортирует структуры метаданных для настройки производительности поиска во время импорта.</span><span class="sxs-lookup"><span data-stu-id="c0b36-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="c0b36-118">Этот шаг обычно приводит к переносу записей, с побочным эффектом, что маркеров, сохраненных с помощью средства для дальнейшего становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="c0b36-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="c0b36-119">Метаданные не сообщающий вызывающему объекту этих изменениях маркера до выполнения второй передачи, тем не менее.</span><span class="sxs-lookup"><span data-stu-id="c0b36-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="c0b36-120">На втором этапе выполняются различные операции, которые призваны уменьшить общий размер метаданных, как оптимизация (ранняя привязка) `mdTypeRef` и `mdMemberRef` маркеры, если ссылка указывает на тип или член, объявленный в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="c0b36-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="c0b36-121">На этом этапе возникает другой цикл сопоставления маркеров.</span><span class="sxs-lookup"><span data-stu-id="c0b36-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="c0b36-122">После этого этапа ядро метаданных уведомляет вызывающего объекта, через его `IMapToken` интерфейс любого изменения значений маркера.</span><span class="sxs-lookup"><span data-stu-id="c0b36-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0b36-123">Требования</span><span class="sxs-lookup"><span data-stu-id="c0b36-123">Requirements</span></span>  
 <span data-ttu-id="c0b36-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0b36-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0b36-125">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0b36-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0b36-126">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c0b36-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0b36-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0b36-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0b36-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c0b36-128">See also</span></span>

- [<span data-ttu-id="c0b36-129">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c0b36-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c0b36-130">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c0b36-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
