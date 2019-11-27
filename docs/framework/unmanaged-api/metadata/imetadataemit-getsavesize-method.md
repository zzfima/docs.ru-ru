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
ms.openlocfilehash: 125a63638a41707b8eed918253cb1f93abb907eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434334"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="2342c-102">Метод IMetaDataEmit::GetSaveSize</span><span class="sxs-lookup"><span data-stu-id="2342c-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="2342c-103">Возвращает приблизительный двоичный размер сборки и ее метаданных в текущей области.</span><span class="sxs-lookup"><span data-stu-id="2342c-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2342c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2342c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2342c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2342c-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="2342c-106">окне Значение перечисления [корсавесизе](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) , указывающее, следует ли получить точный или приблизительный размер.</span><span class="sxs-lookup"><span data-stu-id="2342c-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="2342c-107">Допустимы только три значения: Кссаккурате, Ксскуикк и Кссдискардтрансиенткас:</span><span class="sxs-lookup"><span data-stu-id="2342c-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
- <span data-ttu-id="2342c-108">Кссаккурате возвращает точный размер сохранения, но для его вычисления требуется больше времени.</span><span class="sxs-lookup"><span data-stu-id="2342c-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
- <span data-ttu-id="2342c-109">Ксскуикк возвращает размер, дополненный для безопасности, но требует меньше времени для вычисления.</span><span class="sxs-lookup"><span data-stu-id="2342c-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
- <span data-ttu-id="2342c-110">Кссдискардтрансиенткас сообщает `GetSaveSize`, что он может создавать неразрешенные настраиваемые атрибуты.</span><span class="sxs-lookup"><span data-stu-id="2342c-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="2342c-111">заполняет Указатель на размер, необходимый для сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="2342c-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2342c-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="2342c-112">Remarks</span></span>  
 <span data-ttu-id="2342c-113">`GetSaveSize` вычисляет пространство, необходимое в байтах, для сохранения сборки и всех ее метаданных в текущей области.</span><span class="sxs-lookup"><span data-stu-id="2342c-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="2342c-114">(Вызов метода [IMetaDataEmit:: саветостреам](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) приведет к порождению этого числа байтов.)</span><span class="sxs-lookup"><span data-stu-id="2342c-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="2342c-115">Если вызывающий объект реализует интерфейс [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) (через [IMetaDataEmit:: сесандлер](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) или [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` выполняет два прохода по метаданным для оптимизации и сжатия.</span><span class="sxs-lookup"><span data-stu-id="2342c-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="2342c-116">В противном случае оптимизация не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2342c-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="2342c-117">Если выполняется оптимизация, первый проход просто сортирует структуры метаданных для настройки производительности поисков во время поиска.</span><span class="sxs-lookup"><span data-stu-id="2342c-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="2342c-118">Этот шаг обычно приводит к перемещению записей, с побочным действием, что токены, сохраняемые средством для будущего использования, становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="2342c-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="2342c-119">Однако метаданные не сообщают вызывающему объекту об изменениях токена до второго прохода.</span><span class="sxs-lookup"><span data-stu-id="2342c-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="2342c-120">Во втором прохождении выполняются различные оптимизации, предназначенные для уменьшения общего размера метаданных, например для оптимизации (раннее связывание) `mdTypeRef` и `mdMemberRef` токены, если ссылка относится к типу или члену, объявленному в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="2342c-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="2342c-121">На этом этапе выполняется еще один цикл сопоставления маркеров.</span><span class="sxs-lookup"><span data-stu-id="2342c-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="2342c-122">После этого обработчик метаданных уведомляет вызывающий объект, используя его интерфейс `IMapToken`, для любых измененных значений токенов.</span><span class="sxs-lookup"><span data-stu-id="2342c-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2342c-123">Требования</span><span class="sxs-lookup"><span data-stu-id="2342c-123">Requirements</span></span>  
 <span data-ttu-id="2342c-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2342c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2342c-125">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="2342c-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2342c-126">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2342c-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2342c-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2342c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2342c-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="2342c-128">See also</span></span>

- [<span data-ttu-id="2342c-129">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2342c-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2342c-130">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2342c-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
