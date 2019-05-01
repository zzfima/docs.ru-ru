---
title: Метод ISymUnmanagedWriter::OpenNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1585acce8bba0dff327c961f5e32ef6b46794401
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986028"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="dac22-102">Метод ISymUnmanagedWriter::OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="dac22-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="dac22-103">Открывает новое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="dac22-103">Opens a new namespace.</span></span> <span data-ttu-id="dac22-104">Этот метод следует вызывайте перед определением методов или переменных, расположенных в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="dac22-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="dac22-105">Пространства имен могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="dac22-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dac22-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dac22-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dac22-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="dac22-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="dac22-108">[in] Указатель на имя нового пространства имен.</span><span class="sxs-lookup"><span data-stu-id="dac22-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dac22-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dac22-109">Return Value</span></span>  
 <span data-ttu-id="dac22-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="dac22-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dac22-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dac22-111">Requirements</span></span>  
 <span data-ttu-id="dac22-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dac22-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac22-113">См. также</span><span class="sxs-lookup"><span data-stu-id="dac22-113">See also</span></span>

- [<span data-ttu-id="dac22-114">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="dac22-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="dac22-115">Метод CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="dac22-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
