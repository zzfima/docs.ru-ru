---
title: Метод ISymUnmanagedNamespace::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 039dab1b4ca86cb26de739e74b152f108f074c43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426176"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="fd573-102">Метод ISymUnmanagedNamespace::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="fd573-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="fd573-103">Возвращает дочерние элементы этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fd573-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd573-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd573-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd573-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd573-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="fd573-106">[in] Объект `ULONG32` указывает размер `namespaces` массива.</span><span class="sxs-lookup"><span data-stu-id="fd573-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="fd573-107">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, необходимый для содержания пространств имен.</span><span class="sxs-lookup"><span data-stu-id="fd573-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="fd573-108">[out] Указатель на буфер, содержащий пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fd573-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd573-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd573-109">Return Value</span></span>  
 <span data-ttu-id="fd573-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="fd573-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd573-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fd573-111">Requirements</span></span>  
 <span data-ttu-id="fd573-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fd573-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd573-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fd573-113">See Also</span></span>  
 [<span data-ttu-id="fd573-114">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="fd573-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
