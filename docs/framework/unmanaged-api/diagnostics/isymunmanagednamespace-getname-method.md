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
ms.openlocfilehash: aeb3c4e9a1d87b2d93a310b88c340aec0955a845
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425302"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="33eaa-102">Метод ISymUnmanagedNamespace::GetName</span><span class="sxs-lookup"><span data-stu-id="33eaa-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="33eaa-103">Возвращает имя этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="33eaa-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33eaa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33eaa-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33eaa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="33eaa-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="33eaa-106">[in] Объект `ULONG32` указывает размер `szName` буфера.</span><span class="sxs-lookup"><span data-stu-id="33eaa-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="33eaa-107">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, должны содержать имя пространства имен, включая нулем.</span><span class="sxs-lookup"><span data-stu-id="33eaa-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="33eaa-108">[out] Указатель на буфер, содержащий имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="33eaa-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33eaa-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="33eaa-109">Return Value</span></span>  
 <span data-ttu-id="33eaa-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="33eaa-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33eaa-111">Требования</span><span class="sxs-lookup"><span data-stu-id="33eaa-111">Requirements</span></span>  
 <span data-ttu-id="33eaa-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="33eaa-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33eaa-113">См. также</span><span class="sxs-lookup"><span data-stu-id="33eaa-113">See Also</span></span>  
 [<span data-ttu-id="33eaa-114">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="33eaa-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
