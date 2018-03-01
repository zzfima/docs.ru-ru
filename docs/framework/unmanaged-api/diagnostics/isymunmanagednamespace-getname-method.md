---
title: "Метод ISymUnmanagedNamespace::GetName"
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
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 37b29e71a9a1185a7080f71b1621a07dd7ae41a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="fe70a-102">Метод ISymUnmanagedNamespace::GetName</span><span class="sxs-lookup"><span data-stu-id="fe70a-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="fe70a-103">Возвращает имя этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fe70a-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe70a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe70a-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe70a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe70a-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="fe70a-106">[in] Объект `ULONG32` указывает размер `szName` буфера.</span><span class="sxs-lookup"><span data-stu-id="fe70a-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="fe70a-107">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, должны содержать имя пространства имен, включая нулем.</span><span class="sxs-lookup"><span data-stu-id="fe70a-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="fe70a-108">[out] Указатель на буфер, содержащий имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fe70a-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe70a-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fe70a-109">Return Value</span></span>  
 <span data-ttu-id="fe70a-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="fe70a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe70a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fe70a-111">Requirements</span></span>  
 <span data-ttu-id="fe70a-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fe70a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe70a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fe70a-113">See Also</span></span>  
 [<span data-ttu-id="fe70a-114">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="fe70a-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
