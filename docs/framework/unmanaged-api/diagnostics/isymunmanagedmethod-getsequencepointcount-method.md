---
title: Метод ISymUnmanagedMethod::GetSequencePointCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePointCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9eac17ec9599caba88ddaa73d28abcae538a4d19
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215070"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="7b700-102">Метод ISymUnmanagedMethod::GetSequencePointCount</span><span class="sxs-lookup"><span data-stu-id="7b700-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="7b700-103">Возвращает число точек следования в этот метод.</span><span class="sxs-lookup"><span data-stu-id="7b700-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b700-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b700-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b700-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b700-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7b700-106">[out] Указатель на `ULONG32` , получающий размер буфера, необходимый для точек следования.</span><span class="sxs-lookup"><span data-stu-id="7b700-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b700-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7b700-107">Return Value</span></span>  
 <span data-ttu-id="7b700-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="7b700-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b700-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7b700-109">Requirements</span></span>  
 <span data-ttu-id="7b700-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7b700-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b700-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7b700-111">See also</span></span>

- [<span data-ttu-id="7b700-112">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="7b700-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
