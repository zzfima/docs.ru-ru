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
ms.openlocfilehash: 4d3c3c0c5634653d14577de9a1334048d75216b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405630"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="f4147-102">Метод ICorDebugClass::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="f4147-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="f4147-103">Получает значение указанного статического поля.</span><span class="sxs-lookup"><span data-stu-id="f4147-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4147-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4147-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4147-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4147-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="f4147-106">[in] Поле `Def` маркер, который ссылается на поле должно быть извлечено.</span><span class="sxs-lookup"><span data-stu-id="f4147-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="f4147-107">[in] Указатель на объект ICorDebugFrame, который представляет кадр, используемый для однозначного определения потока, контекста или статических переменных для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="f4147-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="f4147-108">Если поле является статическим относительно потока, контекста или домена приложения, кадр определит соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="f4147-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f4147-109">[out] Указатель на адрес объекта ICorDebugValue, представляющий значение статического поля.</span><span class="sxs-lookup"><span data-stu-id="f4147-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4147-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4147-110">Remarks</span></span>  
 <span data-ttu-id="f4147-111">Для параметризированных типов значение статического поля — относительно определенного процесса создания экземпляров.</span><span class="sxs-lookup"><span data-stu-id="f4147-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="f4147-112">Таким образом Если конструктор классов принимает параметры типа <xref:System.Type>, вызовите [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) вместо `ICorDebugClass::GetStaticFieldValue`.</span><span class="sxs-lookup"><span data-stu-id="f4147-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4147-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f4147-113">Requirements</span></span>  
 <span data-ttu-id="f4147-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4147-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4147-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4147-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4147-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4147-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4147-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4147-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
