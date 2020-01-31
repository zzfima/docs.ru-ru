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
ms.openlocfilehash: 37bf5abf66b613d8432af84c7d73aff60e9127cb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791276"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="e9a9b-102">Метод ICorDebugType::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="e9a9b-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="e9a9b-103">Возвращает указатель интерфейса на объект ICorDebugValue, содержащий значение статического поля, на которое ссылается заданный токен поля в указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="e9a9b-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9a9b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9a9b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9a9b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9a9b-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="e9a9b-106">окне Токен `mdFieldDef`, указывающий статическое поле.</span><span class="sxs-lookup"><span data-stu-id="e9a9b-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="e9a9b-107">окне Указатель на объект ICorDebugFrame, представляющий кадр стека.</span><span class="sxs-lookup"><span data-stu-id="e9a9b-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e9a9b-108">заполняет Указатель на адрес `ICorDebugValue`, который содержит значение статического поля.</span><span class="sxs-lookup"><span data-stu-id="e9a9b-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9a9b-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="e9a9b-109">Remarks</span></span>  
 <span data-ttu-id="e9a9b-110">Метод `GetStaticFieldValue` можно использовать только в том случае, если тип является ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, как показано в методе [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e9a9b-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="e9a9b-111">Для неуниверсальных типов операция, выполняемая `GetStaticFieldValue`, идентична вызову [ICorDebugClass:: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) для объекта ICorDebugClass, возвращаемого методами [ICorDebugType::](icordebugtype-getclass-method.md)GetObject.</span><span class="sxs-lookup"><span data-stu-id="e9a9b-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="e9a9b-112">Для универсальных типов значение статического поля будет относиться к определенному экземпляру.</span><span class="sxs-lookup"><span data-stu-id="e9a9b-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="e9a9b-113">Кроме того, если статическое поле может быть связано с потоком, контекстом или доменом приложения, то кадр стека поможет отладчику определить правильное значение.</span><span class="sxs-lookup"><span data-stu-id="e9a9b-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9a9b-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="e9a9b-114">Remarks</span></span>  
 <span data-ttu-id="e9a9b-115">`GetStaticFieldValue` можно использовать только в том случае, если вызов метода `ICorDebugType::GetType` возвращает значение ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE.</span><span class="sxs-lookup"><span data-stu-id="e9a9b-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9a9b-116">Требования</span><span class="sxs-lookup"><span data-stu-id="e9a9b-116">Requirements</span></span>  
 <span data-ttu-id="e9a9b-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9a9b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9a9b-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9a9b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9a9b-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9a9b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9a9b-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9a9b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
