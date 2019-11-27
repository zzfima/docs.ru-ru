---
title: Метод ISymUnmanagedVariable::GetAttributes
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
ms.openlocfilehash: cfc28dfcda7bf4b3d1fc6fe3530a212ee76fadd2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446086"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="b52e4-102">Метод ISymUnmanagedVariable::GetAttributes</span><span class="sxs-lookup"><span data-stu-id="b52e4-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="b52e4-103">Возвращает флаги атрибута для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="b52e4-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b52e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b52e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b52e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b52e4-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b52e4-106">заполняет Указатель на `ULONG32`, который получает атрибуты.</span><span class="sxs-lookup"><span data-stu-id="b52e4-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="b52e4-107">Возвращаемое значение будет одним из значений, определенных в перечислении [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b52e4-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b52e4-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b52e4-108">Return Value</span></span>  
 <span data-ttu-id="b52e4-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b52e4-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b52e4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b52e4-110">Requirements</span></span>  
 <span data-ttu-id="b52e4-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="b52e4-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b52e4-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="b52e4-112">See also</span></span>

- [<span data-ttu-id="b52e4-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="b52e4-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
