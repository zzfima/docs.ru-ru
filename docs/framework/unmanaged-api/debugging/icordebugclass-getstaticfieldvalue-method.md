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
ms.openlocfilehash: 873dd5a1eb2c9356049d2d0c0cb495b963c2ae46
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784191"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="b8faa-102">Метод ICorDebugClass::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="b8faa-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="b8faa-103">Возвращает значение указанного статического поля.</span><span class="sxs-lookup"><span data-stu-id="b8faa-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8faa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8faa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8faa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8faa-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="b8faa-106">окне Поле `Def` токен, ссылающийся на извлекаемое поле.</span><span class="sxs-lookup"><span data-stu-id="b8faa-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="b8faa-107">окне Указатель на объект ICorDebugFrame, представляющий кадр, который будет использоваться для однозначного определения статических элементов потока, контекста или домена приложения.</span><span class="sxs-lookup"><span data-stu-id="b8faa-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="b8faa-108">Если статическое поле задается относительно потока, контекста или домена приложения, кадр определит правильное значение.</span><span class="sxs-lookup"><span data-stu-id="b8faa-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b8faa-109">заполняет Указатель на адрес объекта ICorDebugValue, который представляет значение статического поля.</span><span class="sxs-lookup"><span data-stu-id="b8faa-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8faa-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="b8faa-110">Remarks</span></span>  
 <span data-ttu-id="b8faa-111">Для параметризованных типов значение статического поля задается относительно конкретного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b8faa-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="b8faa-112">Таким образом, если конструктор класса принимает параметры типа <xref:System.Type>, вызовите метод [ICorDebugType:: GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) вместо `ICorDebugClass::GetStaticFieldValue`.</span><span class="sxs-lookup"><span data-stu-id="b8faa-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8faa-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b8faa-113">Requirements</span></span>  
 <span data-ttu-id="b8faa-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8faa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8faa-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8faa-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8faa-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8faa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8faa-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8faa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
