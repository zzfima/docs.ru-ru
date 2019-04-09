---
title: Метод ISymUnmanagedWriter2::DefineGlobalVariable2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6bc6c52374ea047d2e76d346ee8bbc3faaa7bb2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145227"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="d09df-102">Метод ISymUnmanagedWriter2::DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="d09df-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="d09df-103">Определяет одну глобальную переменную.</span><span class="sxs-lookup"><span data-stu-id="d09df-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d09df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d09df-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d09df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d09df-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d09df-106">[in] Имя глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="d09df-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="d09df-107">[in] Атрибутов глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="d09df-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="d09df-108">[in] Маркер метаданных для подписи.</span><span class="sxs-lookup"><span data-stu-id="d09df-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="d09df-109">[in] Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="d09df-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="d09df-110">[in] Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="d09df-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="d09df-111">[in] Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="d09df-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="d09df-112">[in] Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="d09df-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d09df-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d09df-113">Return Value</span></span>  
 <span data-ttu-id="d09df-114">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="d09df-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d09df-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d09df-115">Requirements</span></span>  
 <span data-ttu-id="d09df-116">**Заголовок.** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="d09df-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d09df-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d09df-117">See also</span></span>

- [<span data-ttu-id="d09df-118">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="d09df-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="d09df-119">Метод DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="d09df-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
