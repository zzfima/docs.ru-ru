---
title: Метод IMetaDataEmit::MergeEnd
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 277e7e57ae01128039c3a280158110acde3363a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944551"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="960a5-102">Метод IMetaDataEmit::MergeEnd</span><span class="sxs-lookup"><span data-stu-id="960a5-102">IMetaDataEmit::MergeEnd Method</span></span>
<span data-ttu-id="960a5-103">Выполняет слияние в текущей области все области метаданных, определяемое один или несколько предыдущих вызовов [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="960a5-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="960a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="960a5-104">Syntax</span></span>  
  
```  
HRESULT MergeEnd ();  
```  
  
## <a name="parameters"></a><span data-ttu-id="960a5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="960a5-105">Parameters</span></span>  
 <span data-ttu-id="960a5-106">Этот метод не принимает параметров.</span><span class="sxs-lookup"><span data-stu-id="960a5-106">This method takes no parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="960a5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="960a5-107">Remarks</span></span>  
 <span data-ttu-id="960a5-108">Эта процедура включает фактическое слияние метаданных, всех импорта области, указанные перед вызовы `IMetaDataEmit::Merge`, в текущей области вывода.</span><span class="sxs-lookup"><span data-stu-id="960a5-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>  
  
 <span data-ttu-id="960a5-109">Следующие специальные условия для слияния.</span><span class="sxs-lookup"><span data-stu-id="960a5-109">The following special conditions apply to the merge:</span></span>  
  
- <span data-ttu-id="960a5-110">Идентификатор версии модуля (MVID) никогда не импортируется, так как он уникален для метаданных в импортируемой области.</span><span class="sxs-lookup"><span data-stu-id="960a5-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>  
  
- <span data-ttu-id="960a5-111">Нет существующих свойств на уровне модуля, перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="960a5-111">No existing module-wide properties are overwritten.</span></span>  
  
     <span data-ttu-id="960a5-112">Если уже были заданы свойства модуля в текущей области, свойства модуля не импортируются.</span><span class="sxs-lookup"><span data-stu-id="960a5-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="960a5-113">Тем не менее если не были настроены свойства модуля в текущей области, они импортируются только один раз, когда они встречаются впервые.</span><span class="sxs-lookup"><span data-stu-id="960a5-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="960a5-114">Если эти свойства модуля встречаются снова, они являются дубликатами.</span><span class="sxs-lookup"><span data-stu-id="960a5-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="960a5-115">Если сравниваются значения всех свойств модуля (за исключением MVID) и не найден, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="960a5-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>  
  
- <span data-ttu-id="960a5-116">Для определения типов (`TypeDef`), без дубликатов, объединяются в текущей области.</span><span class="sxs-lookup"><span data-stu-id="960a5-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="960a5-117">`TypeDef` объекты проверить наличие дублирующихся с каждым *имя полного объекта* + *GUID* + *номер версии*.</span><span class="sxs-lookup"><span data-stu-id="960a5-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="960a5-118">Если совпадения по имени или идентификатора GUID и любых других двух элементов отличается, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="960a5-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="960a5-119">В противном случае, если все три элемента совпадают, `MergeEnd` проверяет проводится поверхностное для обеспечения записи действительно являются дубликатами; в противном случае возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="960a5-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="960a5-120">Эта проверка проводится поверхностное ищет:</span><span class="sxs-lookup"><span data-stu-id="960a5-120">This cursory check looks for:</span></span>  
  
    - <span data-ttu-id="960a5-121">Же объявления членов, в том же порядке.</span><span class="sxs-lookup"><span data-stu-id="960a5-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="960a5-122">Члены, помеченные как `mdPrivateScope` (см. в разделе [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) перечисления) не включаются в эту проверку; они специально объединяются.</span><span class="sxs-lookup"><span data-stu-id="960a5-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>  
  
    - <span data-ttu-id="960a5-123">Тот же макет класса.</span><span class="sxs-lookup"><span data-stu-id="960a5-123">The same class layout.</span></span>  
  
     <span data-ttu-id="960a5-124">Это означает, что `TypeDef` объект должен быть полностью и согласованно определена в каждой области метаданных в котором она объявлена; если его реализация члена (для класса) распределяются по несколько блоков компиляции, полное определение считается в каждой области, а не добавочное, для каждой области.</span><span class="sxs-lookup"><span data-stu-id="960a5-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="960a5-125">Например если имена параметров относятся к контракту, они должны выдавать одинаково во всех областях; Если они не существенны, они не должны выдаваться в метаданные.</span><span class="sxs-lookup"><span data-stu-id="960a5-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>  
  
     <span data-ttu-id="960a5-126">Исключение, `TypeDef` объект может иметь добавочных членов, отмеченных как `mdPrivateScope`.</span><span class="sxs-lookup"><span data-stu-id="960a5-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="960a5-127">Такие, `MergeEnd` добавляет их в текущую область, без учета того, повторяющиеся значения.</span><span class="sxs-lookup"><span data-stu-id="960a5-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="960a5-128">Так как компилятор распознает частной области, компилятор должен быть отвечают за принудительное применение правил.</span><span class="sxs-lookup"><span data-stu-id="960a5-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>  
  
- <span data-ttu-id="960a5-129">Относительные виртуальные адреса (RVA) не импортируются и объединить; компилятор должен повторно создать эту информацию.</span><span class="sxs-lookup"><span data-stu-id="960a5-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>  
  
- <span data-ttu-id="960a5-130">Настраиваемые атрибуты объединяются только в том случае, если объединить элемента, к которому они подключены.</span><span class="sxs-lookup"><span data-stu-id="960a5-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="960a5-131">Например настраиваемые атрибуты, связанные с классом объединяются при класса встретилось первым.</span><span class="sxs-lookup"><span data-stu-id="960a5-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="960a5-132">Если настраиваемые атрибуты, связанные с `TypeDef` или `MemberDef` предназначена для блока компиляции (например, отметка времени компиляции члена), они не объединяются и само компилятор просьбой удалить или обновить эти данные.</span><span class="sxs-lookup"><span data-stu-id="960a5-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="960a5-133">Требования</span><span class="sxs-lookup"><span data-stu-id="960a5-133">Requirements</span></span>  
 <span data-ttu-id="960a5-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="960a5-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="960a5-135">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="960a5-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="960a5-136">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="960a5-136">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="960a5-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="960a5-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="960a5-138">См. также</span><span class="sxs-lookup"><span data-stu-id="960a5-138">See also</span></span>

- [<span data-ttu-id="960a5-139">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="960a5-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="960a5-140">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="960a5-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
