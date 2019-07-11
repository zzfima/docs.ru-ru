---
title: Метод ISymUnmanagedNamespace::GetName
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4323423d3958fa1ca652c55f8f75749bb6e1ee79
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759385"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="49f6e-102">Метод ISymUnmanagedNamespace::GetName</span><span class="sxs-lookup"><span data-stu-id="49f6e-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="49f6e-103">Возвращает имя этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="49f6e-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49f6e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49f6e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49f6e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49f6e-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="49f6e-106">[in] Объект `ULONG32` указывает размер `szName` буфера.</span><span class="sxs-lookup"><span data-stu-id="49f6e-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="49f6e-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, должны содержать имя пространства имен, включая завершающимся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="49f6e-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="49f6e-108">[out] Указатель на буфер, содержащий имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="49f6e-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49f6e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49f6e-109">Return Value</span></span>  
 <span data-ttu-id="49f6e-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="49f6e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49f6e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="49f6e-111">Requirements</span></span>  
 <span data-ttu-id="49f6e-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="49f6e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f6e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="49f6e-113">See also</span></span>

- [<span data-ttu-id="49f6e-114">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="49f6e-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
