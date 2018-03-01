---
title: "Метод ISymUnmanagedReader::GetNamespaces"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9db8875acfd4df2cd889cc2e6d606aba252fa33f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="ee0f1-102">Метод ISymUnmanagedReader::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="ee0f1-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="ee0f1-103">Возвращает пространства имен, определенные в глобальной области в данном хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="ee0f1-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee0f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee0f1-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee0f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee0f1-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="ee0f1-106">[in] Размер массива пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ee0f1-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="ee0f1-107">[out] Указатель на переменную, которая получает длину списка пространств имен.</span><span class="sxs-lookup"><span data-stu-id="ee0f1-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="ee0f1-108">[out] Указатель на переменную, которая получает список пространств имен.</span><span class="sxs-lookup"><span data-stu-id="ee0f1-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee0f1-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ee0f1-109">Return Value</span></span>  
 <span data-ttu-id="ee0f1-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="ee0f1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee0f1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ee0f1-111">Requirements</span></span>  
 <span data-ttu-id="ee0f1-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ee0f1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee0f1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ee0f1-113">See Also</span></span>  
 [<span data-ttu-id="ee0f1-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="ee0f1-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
