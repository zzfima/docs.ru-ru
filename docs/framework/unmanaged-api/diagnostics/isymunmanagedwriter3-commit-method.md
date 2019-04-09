---
title: Метод ISymUnmanagedWriter3::Commit
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.Commit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f531b96211a1dd6072d62937b9f93fc17f105d4d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149049"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="18445-102">Метод ISymUnmanagedWriter3::Commit</span><span class="sxs-lookup"><span data-stu-id="18445-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="18445-103">Фиксирует изменения, записанных в поток.</span><span class="sxs-lookup"><span data-stu-id="18445-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18445-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18445-104">Syntax</span></span>  
  
```  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="18445-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="18445-105">Return Value</span></span>  
 <span data-ttu-id="18445-106">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="18445-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18445-107">Требования</span><span class="sxs-lookup"><span data-stu-id="18445-107">Requirements</span></span>  
 <span data-ttu-id="18445-108">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="18445-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18445-109">См. также</span><span class="sxs-lookup"><span data-stu-id="18445-109">See also</span></span>

- [<span data-ttu-id="18445-110">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="18445-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
