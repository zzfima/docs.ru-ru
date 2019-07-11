---
title: Метод ICorDebugClass::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7649d91ca2b654952d1d5ab0d45f7903d3c46a32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745542"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="9ae38-102">Метод ICorDebugClass::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="9ae38-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="9ae38-103">Получает значение указанного статического поля.</span><span class="sxs-lookup"><span data-stu-id="9ae38-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ae38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ae38-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ae38-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ae38-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="9ae38-106">[in] Поле `Def` маркер, который ссылается на поля для извлечения.</span><span class="sxs-lookup"><span data-stu-id="9ae38-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="9ae38-107">[in] Указатель на интерфейс ICorDebugFrame объект, представляющий кадр и использоваться для однозначного определения потока, контекста или статических элементов домена приложения.</span><span class="sxs-lookup"><span data-stu-id="9ae38-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="9ae38-108">Если поле является статическим относительно потока, контекста или домена приложения, кадр определит соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="9ae38-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="9ae38-109">[out] Указатель на адрес ICorDebugValue объект, представляющий значение статического поля.</span><span class="sxs-lookup"><span data-stu-id="9ae38-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ae38-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9ae38-110">Remarks</span></span>  
 <span data-ttu-id="9ae38-111">Для параметризованных типов значение статического поля задается относительно определенного процесса создания экземпляров.</span><span class="sxs-lookup"><span data-stu-id="9ae38-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="9ae38-112">Таким образом Если конструктор классов принимает параметры типа <xref:System.Type>, вызовите [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) вместо `ICorDebugClass::GetStaticFieldValue`.</span><span class="sxs-lookup"><span data-stu-id="9ae38-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ae38-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9ae38-113">Requirements</span></span>  
 <span data-ttu-id="9ae38-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ae38-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ae38-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ae38-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ae38-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ae38-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ae38-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ae38-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
