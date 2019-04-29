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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7ba794060330de3934f8d4ca6434b09672d12bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797570"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="e3ad2-102">Метод ISymUnmanagedVariable::GetAttributes</span><span class="sxs-lookup"><span data-stu-id="e3ad2-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="e3ad2-103">Возвращает флаги атрибутов для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="e3ad2-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3ad2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3ad2-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3ad2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3ad2-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e3ad2-106">[out] Указатель на `ULONG32` , получающий атрибуты.</span><span class="sxs-lookup"><span data-stu-id="e3ad2-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="e3ad2-107">Возвращаемое значение будет иметь одно из значений, определенных в [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="e3ad2-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3ad2-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e3ad2-108">Return Value</span></span>  
 <span data-ttu-id="e3ad2-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="e3ad2-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3ad2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e3ad2-110">Requirements</span></span>  
 <span data-ttu-id="e3ad2-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e3ad2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ad2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e3ad2-112">See also</span></span>

- [<span data-ttu-id="e3ad2-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="e3ad2-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
