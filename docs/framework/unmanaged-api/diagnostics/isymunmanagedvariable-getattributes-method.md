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
ms.openlocfilehash: d418a1088f9ee23a088ab4c8246810d2c9bee4fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574343"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="32bd3-102">Метод ISymUnmanagedVariable::GetAttributes</span><span class="sxs-lookup"><span data-stu-id="32bd3-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="32bd3-103">Возвращает флаги атрибутов для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="32bd3-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32bd3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32bd3-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32bd3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="32bd3-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="32bd3-106">[out] Указатель на `ULONG32` , получающий атрибуты.</span><span class="sxs-lookup"><span data-stu-id="32bd3-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="32bd3-107">Возвращаемое значение будет иметь одно из значений, определенных в [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="32bd3-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32bd3-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="32bd3-108">Return Value</span></span>  
 <span data-ttu-id="32bd3-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="32bd3-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32bd3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="32bd3-110">Requirements</span></span>  
 <span data-ttu-id="32bd3-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="32bd3-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32bd3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="32bd3-112">See also</span></span>
- [<span data-ttu-id="32bd3-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="32bd3-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
