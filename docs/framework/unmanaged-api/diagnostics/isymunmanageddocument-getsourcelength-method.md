---
title: "Метод ISymUnmanagedDocument::GetSourceLength"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetSourceLength
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61d9bd99a08f428993f38fb5b6889c9659607782
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="dc723-102">Метод ISymUnmanagedDocument::GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="dc723-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="dc723-103">Возвращает длину внедренного источника в байтах.</span><span class="sxs-lookup"><span data-stu-id="dc723-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc723-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc723-104">Syntax</span></span>  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dc723-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dc723-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="dc723-106">[out] Указатель на переменную, которая указывает длину внедренного источника, в байтах.</span><span class="sxs-lookup"><span data-stu-id="dc723-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc723-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dc723-107">Return Value</span></span>  
 <span data-ttu-id="dc723-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="dc723-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc723-109">См. также</span><span class="sxs-lookup"><span data-stu-id="dc723-109">See Also</span></span>  
 [<span data-ttu-id="dc723-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="dc723-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
