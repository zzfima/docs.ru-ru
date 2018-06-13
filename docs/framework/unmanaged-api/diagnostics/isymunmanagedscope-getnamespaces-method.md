---
title: Метод ISymUnmanagedScope::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c786cd43a25aa0c69c19e57452a3b190c7bfb167
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426845"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="04f2b-102">Метод ISymUnmanagedScope::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="04f2b-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="04f2b-103">Возвращает пространства имен, используемые в этой области.</span><span class="sxs-lookup"><span data-stu-id="04f2b-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04f2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04f2b-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04f2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04f2b-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="04f2b-106">[in] Размер массива `namespaces`.</span><span class="sxs-lookup"><span data-stu-id="04f2b-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="04f2b-107">[out] Указатель на `ULONG32` , получающий размер буфера, необходимый для пространства имен.</span><span class="sxs-lookup"><span data-stu-id="04f2b-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="04f2b-108">[out] Массив, получающий пространства имен.</span><span class="sxs-lookup"><span data-stu-id="04f2b-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04f2b-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="04f2b-109">Return Value</span></span>  
 <span data-ttu-id="04f2b-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="04f2b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04f2b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="04f2b-111">Requirements</span></span>  
 <span data-ttu-id="04f2b-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="04f2b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f2b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="04f2b-113">See Also</span></span>  
 [<span data-ttu-id="04f2b-114">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="04f2b-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
