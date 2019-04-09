---
title: Метод ISymUnmanagedWriter2::DefineConstant2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e9bff5be747c4872554a69dd316de8ca9eb9934
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198937"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="724c7-102">Метод ISymUnmanagedWriter2::DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="724c7-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="724c7-103">Определяет имя для значения константы.</span><span class="sxs-lookup"><span data-stu-id="724c7-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="724c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="724c7-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="724c7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="724c7-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="724c7-106">[in] Постоянное имя.</span><span class="sxs-lookup"><span data-stu-id="724c7-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="724c7-107">[in] Значение константы.</span><span class="sxs-lookup"><span data-stu-id="724c7-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="724c7-108">[in] Токен метаданных константы.</span><span class="sxs-lookup"><span data-stu-id="724c7-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="724c7-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="724c7-109">Return Value</span></span>  
 <span data-ttu-id="724c7-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="724c7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="724c7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="724c7-111">Requirements</span></span>  
 <span data-ttu-id="724c7-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="724c7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="724c7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="724c7-113">See also</span></span>

- [<span data-ttu-id="724c7-114">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="724c7-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="724c7-115">Метод DefineConstant</span><span class="sxs-lookup"><span data-stu-id="724c7-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
