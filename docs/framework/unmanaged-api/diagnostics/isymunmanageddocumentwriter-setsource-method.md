---
title: Метод ISymUnmanagedDocumentWriter::SetSource
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f25f66d7092c50247e24051280eaa7b714297c20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="cf79f-102">Метод ISymUnmanagedDocumentWriter::SetSource</span><span class="sxs-lookup"><span data-stu-id="cf79f-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="cf79f-103">Устанавливает внедренный источник документа, который выполняется запись.</span><span class="sxs-lookup"><span data-stu-id="cf79f-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf79f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf79f-104">Syntax</span></span>  
  
```  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf79f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf79f-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="cf79f-106">[in] Объект `ULONG32` , содержащее размер `source` буфера.</span><span class="sxs-lookup"><span data-stu-id="cf79f-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="cf79f-107">[in] Буфера, хранящего внедренного источника.</span><span class="sxs-lookup"><span data-stu-id="cf79f-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf79f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cf79f-108">Return Value</span></span>  
 <span data-ttu-id="cf79f-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="cf79f-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf79f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="cf79f-110">Requirements</span></span>  
 <span data-ttu-id="cf79f-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cf79f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf79f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="cf79f-112">See Also</span></span>  
 [<span data-ttu-id="cf79f-113">Интерфейс ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="cf79f-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
