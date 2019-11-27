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
ms.openlocfilehash: 34ecfc2f01f22971e135358806adeea632e02f8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448039"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="e4902-102">Метод IMetaDataEmit::MergeEnd</span><span class="sxs-lookup"><span data-stu-id="e4902-102">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="e4902-103">Выполняет слияние в текущую область всех областей метаданных, указанных одним или несколькими ранними вызовами метода [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="e4902-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="e4902-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4902-104">Syntax</span></span>

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="e4902-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4902-105">Parameters</span></span>

<span data-ttu-id="e4902-106">Этот метод не принимает параметров.</span><span class="sxs-lookup"><span data-stu-id="e4902-106">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4902-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4902-107">Remarks</span></span>

<span data-ttu-id="e4902-108">Эта подпрограммы запускает фактическое слияние метаданных всех областей импорта, заданных предыдущими вызовами `IMetaDataEmit::Merge`, в текущую область вывода.</span><span class="sxs-lookup"><span data-stu-id="e4902-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="e4902-109">К объединению применяются следующие особые условия.</span><span class="sxs-lookup"><span data-stu-id="e4902-109">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="e4902-110">Идентификатор версии модуля (MVID) никогда не импортируется, так как он уникален для метаданных в области импорта.</span><span class="sxs-lookup"><span data-stu-id="e4902-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="e4902-111">Существующие свойства модуля не перезаписываются.</span><span class="sxs-lookup"><span data-stu-id="e4902-111">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="e4902-112">Если свойства модуля уже заданы для текущей области, свойства модуля не импортируются.</span><span class="sxs-lookup"><span data-stu-id="e4902-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="e4902-113">Однако если свойства модуля не были заданы в текущей области, они импортируются только один раз при первом обнаружении.</span><span class="sxs-lookup"><span data-stu-id="e4902-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="e4902-114">Если эти свойства модуля встречаются снова, они являются повторяющимися.</span><span class="sxs-lookup"><span data-stu-id="e4902-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="e4902-115">Если сравниваются значения всех свойств модуля (кроме MVID) и не найдены дубликаты, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="e4902-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="e4902-116">Для определений типов (`TypeDef`) в текущую область не объединяются дубликаты.</span><span class="sxs-lookup"><span data-stu-id="e4902-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="e4902-117">`TypeDef` объекты проверяются на наличие дубликатов для каждого *полного имени объекта* + *GUID* + *номер версии*.</span><span class="sxs-lookup"><span data-stu-id="e4902-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="e4902-118">Если существует совпадение с именем или идентификатором GUID, а любой из двух других элементов отличается, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="e4902-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="e4902-119">В противном случае, если все три элемента совпадают, `MergeEnd` выполняет проверку курсора, чтобы убедиться, что записи действительно являются повторяющимися. в противном случае возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="e4902-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="e4902-120">Эта проверка курсора ищет:</span><span class="sxs-lookup"><span data-stu-id="e4902-120">This cursory check looks for:</span></span>

  - <span data-ttu-id="e4902-121">Одни и те же объявления членов, происходящие в том же порядке.</span><span class="sxs-lookup"><span data-stu-id="e4902-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="e4902-122">Элементы, помеченные как `mdPrivateScope` (см. Перечисление [кормесодаттр](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) ), не включаются в эту проверку. они объединяются специально.</span><span class="sxs-lookup"><span data-stu-id="e4902-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="e4902-123">Тот же макет класса.</span><span class="sxs-lookup"><span data-stu-id="e4902-123">The same class layout.</span></span>

  <span data-ttu-id="e4902-124">Это означает, что объект `TypeDef` должен всегда быть полностью и согласованным в каждой области метаданных, в которой он объявлен. Если его реализации (для класса) распределяются между несколькими единицами компиляции, предполагается, что полное определение находится в каждой области и не помещается в каждую область.</span><span class="sxs-lookup"><span data-stu-id="e4902-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="e4902-125">Например, если имена параметров имеют отношение к контракту, они должны выдаваться одинаковым образом в каждую область видимости. Если они не важны, они не должны выдаваться в метаданные.</span><span class="sxs-lookup"><span data-stu-id="e4902-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="e4902-126">Исключением является то, что объект `TypeDef` может иметь инкрементные элементы, помеченные как `mdPrivateScope`.</span><span class="sxs-lookup"><span data-stu-id="e4902-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="e4902-127">При возникновении этих проблем `MergeEnd` постепенно добавляет их в текущую область без учета дубликатов.</span><span class="sxs-lookup"><span data-stu-id="e4902-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="e4902-128">Поскольку компилятор понимает частную область, компилятор должен отвечать за применение правил.</span><span class="sxs-lookup"><span data-stu-id="e4902-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="e4902-129">Относительные виртуальные адреса (RVA) не импортируются и не объединяются; Предполагается, что компилятор повторно выдает эти сведения.</span><span class="sxs-lookup"><span data-stu-id="e4902-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="e4902-130">Пользовательские атрибуты объединяются только при слиянии элемента, к которому они присоединены.</span><span class="sxs-lookup"><span data-stu-id="e4902-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="e4902-131">Например, пользовательские атрибуты, связанные с классом, объединяются при первом обнаружении класса.</span><span class="sxs-lookup"><span data-stu-id="e4902-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="e4902-132">Если настраиваемые атрибуты связаны с `TypeDef` или `MemberDef`, которые относятся к единице компиляции (например, отметка времени для компиляции элемента), они не объединяются и компилятор удаляет или обновляет такие метаданные.</span><span class="sxs-lookup"><span data-stu-id="e4902-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4902-133">Требования</span><span class="sxs-lookup"><span data-stu-id="e4902-133">Requirements</span></span>

<span data-ttu-id="e4902-134">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4902-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="e4902-135">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e4902-135">**Header:** Cor.h</span></span>

<span data-ttu-id="e4902-136">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e4902-136">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="e4902-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4902-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e4902-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="e4902-138">See also</span></span>

- [<span data-ttu-id="e4902-139">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e4902-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e4902-140">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e4902-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
