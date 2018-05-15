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
ms.openlocfilehash: dc0f72168e076f661bfefc17c851d7d353e5e742
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="fc946-102">Метод ISymUnmanagedVariable::GetAttributes</span><span class="sxs-lookup"><span data-stu-id="fc946-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="fc946-103">Получает флаги атрибутов для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="fc946-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc946-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc946-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc946-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc946-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="fc946-106">[out] Указатель на `ULONG32` , получающую атрибуты.</span><span class="sxs-lookup"><span data-stu-id="fc946-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="fc946-107">Возвращаемое значение будет иметь одно из значений, определенных в [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="fc946-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc946-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fc946-108">Return Value</span></span>  
 <span data-ttu-id="fc946-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="fc946-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc946-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fc946-110">Requirements</span></span>  
 <span data-ttu-id="fc946-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fc946-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc946-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fc946-112">See Also</span></span>  
 [<span data-ttu-id="fc946-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="fc946-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
