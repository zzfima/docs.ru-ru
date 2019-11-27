---
title: Метод IMetaDataImport::GetMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: 0542c518b64764ad27aa00b8d595be1191059436
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437446"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="66922-102">Метод IMetaDataImport::GetMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="66922-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="66922-103">Получает флаги, указывающие связь между методом, на который ссылается указанный токен MethodDef, и связанным свойством и событием, на которые ссылается указанный токен Евентпроп.</span><span class="sxs-lookup"><span data-stu-id="66922-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66922-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66922-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66922-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66922-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="66922-106">окне Токен MethodDef, представляющий метод, для которого необходимо получить сведения о семантической роли.</span><span class="sxs-lookup"><span data-stu-id="66922-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="66922-107">окне Токен, представляющий парное свойство и событие, для которого необходимо получить роль метода.</span><span class="sxs-lookup"><span data-stu-id="66922-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="66922-108">заполняет Указатель на соответствующие флаги семантики.</span><span class="sxs-lookup"><span data-stu-id="66922-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="66922-109">Это значение является битовой маской из перечисления [кормесодсемантиксаттр](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="66922-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66922-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="66922-110">Remarks</span></span>  
 <span data-ttu-id="66922-111">Метод [IMetaDataEmit::D ефинепроперти](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) задает флаги семантики метода.</span><span class="sxs-lookup"><span data-stu-id="66922-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66922-112">Требования</span><span class="sxs-lookup"><span data-stu-id="66922-112">Requirements</span></span>  
 <span data-ttu-id="66922-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66922-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66922-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="66922-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66922-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="66922-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66922-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66922-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66922-117">См. также</span><span class="sxs-lookup"><span data-stu-id="66922-117">See also</span></span>

- [<span data-ttu-id="66922-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="66922-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="66922-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="66922-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
