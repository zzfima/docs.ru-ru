---
title: "Метод ICorDebugType::GetStaticFieldValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetStaticFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a6a7305017c83b539a3d5ec11fa61ccd2af90a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="a2410-102">Метод ICorDebugType::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="a2410-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="a2410-103">Получает указатель интерфейса на объект ICorDebugValue, содержащий значение статического поля, который ссылается указанное поле токена в указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="a2410-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2410-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2410-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2410-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2410-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="a2410-106">[in] `mdFieldDef` Маркер, который указывает статического поля.</span><span class="sxs-lookup"><span data-stu-id="a2410-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="a2410-107">[in] Указатель ICorDebugFrame, который представляет кадр стека.</span><span class="sxs-lookup"><span data-stu-id="a2410-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a2410-108">[out] Указатель на адрес `ICorDebugValue` , содержащий значение статического поля.</span><span class="sxs-lookup"><span data-stu-id="a2410-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2410-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2410-109">Remarks</span></span>  
 <span data-ttu-id="a2410-110">`GetStaticFieldValue` Метод может использоваться только в том случае, если тип является ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, как указано в [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a2410-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="a2410-111">Для типов неуниверсальных выполнить операцию по `GetStaticFieldValue` совпадает с вызовом метода [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) ICorDebugClass объекта, который возвращается методом [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="a2410-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="a2410-112">Для универсальных типов значение статического поля будет относительно определенного процесса создания экземпляров.</span><span class="sxs-lookup"><span data-stu-id="a2410-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="a2410-113">Кроме того Если статическое поле может определяться относительно потока, контекста или домена приложения, кадр стека помогает отладчику определить правильное значение.</span><span class="sxs-lookup"><span data-stu-id="a2410-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2410-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2410-114">Remarks</span></span>  
 <span data-ttu-id="a2410-115">`GetStaticFieldValue`можно использовать только при вызове `ICorDebugType::GetType` возвращает значение ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE.</span><span class="sxs-lookup"><span data-stu-id="a2410-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2410-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a2410-116">Requirements</span></span>  
 <span data-ttu-id="a2410-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2410-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2410-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2410-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2410-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2410-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2410-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2410-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
