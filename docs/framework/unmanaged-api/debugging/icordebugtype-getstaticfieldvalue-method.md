---
title: Метод ICorDebugType::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
ms.openlocfilehash: 95183701987d3ddec3835a17c5d256c25c2c4c64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132066"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="7252d-102">Метод ICorDebugType::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="7252d-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="7252d-103">Возвращает указатель интерфейса на объект ICorDebugValue, содержащий значение статического поля, на которое ссылается заданный токен поля в указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="7252d-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7252d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7252d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7252d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7252d-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="7252d-106">окне Токен `mdFieldDef`, указывающий статическое поле.</span><span class="sxs-lookup"><span data-stu-id="7252d-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="7252d-107">окне Указатель на объект ICorDebugFrame, представляющий кадр стека.</span><span class="sxs-lookup"><span data-stu-id="7252d-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="7252d-108">заполняет Указатель на адрес `ICorDebugValue`, который содержит значение статического поля.</span><span class="sxs-lookup"><span data-stu-id="7252d-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7252d-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="7252d-109">Remarks</span></span>  
 <span data-ttu-id="7252d-110">Метод `GetStaticFieldValue` можно использовать, только если тип — ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, как показано в методе [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7252d-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="7252d-111">Для неуниверсальных типов операция, выполняемая `GetStaticFieldValue`, идентична вызову [ICorDebugClass:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) для объекта ICorDebugClass, возвращаемого методами [ICorDebugType::](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)GetObject.</span><span class="sxs-lookup"><span data-stu-id="7252d-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="7252d-112">Для универсальных типов значение статического поля будет относиться к определенному экземпляру.</span><span class="sxs-lookup"><span data-stu-id="7252d-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="7252d-113">Кроме того, если статическое поле может быть связано с потоком, контекстом или доменом приложения, то кадр стека поможет отладчику определить правильное значение.</span><span class="sxs-lookup"><span data-stu-id="7252d-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7252d-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="7252d-114">Remarks</span></span>  
 <span data-ttu-id="7252d-115">`GetStaticFieldValue` можно использовать только в том случае, если вызов метода `ICorDebugType::GetType` возвращает значение ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE.</span><span class="sxs-lookup"><span data-stu-id="7252d-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7252d-116">Требования</span><span class="sxs-lookup"><span data-stu-id="7252d-116">Requirements</span></span>  
 <span data-ttu-id="7252d-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7252d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7252d-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7252d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7252d-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7252d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7252d-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7252d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
