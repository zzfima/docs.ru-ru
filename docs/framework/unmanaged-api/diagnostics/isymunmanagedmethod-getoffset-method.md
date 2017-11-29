---
title: "Метод ISymUnmanagedMethod::GetOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f75236ae954b4ff3df9dd1c322cef45dfaf7fb2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="8ba88-102">Метод ISymUnmanagedMethod::GetOffset</span><span class="sxs-lookup"><span data-stu-id="8ba88-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="8ba88-103">Возвращает смещение в этом методе, соответствующее заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="8ba88-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ba88-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ba88-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ba88-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="8ba88-106">[in] Указатель на документ, для которого запрашивается смещение.</span><span class="sxs-lookup"><span data-stu-id="8ba88-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="8ba88-107">[in] Строка документа, для которого запрашивается смещение.</span><span class="sxs-lookup"><span data-stu-id="8ba88-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="8ba88-108">[in] Столбец документа, для которого запрашивается смещение.</span><span class="sxs-lookup"><span data-stu-id="8ba88-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="8ba88-109">[out] Указатель на `ULONG32` , получающий смещения.</span><span class="sxs-lookup"><span data-stu-id="8ba88-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ba88-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8ba88-110">Return Value</span></span>  
 <span data-ttu-id="8ba88-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="8ba88-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ba88-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8ba88-112">Requirements</span></span>  
 <span data-ttu-id="8ba88-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8ba88-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba88-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8ba88-114">See Also</span></span>  
 [<span data-ttu-id="8ba88-115">ISymUnmanagedMethod-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8ba88-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
