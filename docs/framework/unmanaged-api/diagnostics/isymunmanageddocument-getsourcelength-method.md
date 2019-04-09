---
title: Метод ISymUnmanagedDocument::GetSourceLength
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2717a279abf7fb1b704a769d54654d97949cc0a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136907"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="35736-102">Метод ISymUnmanagedDocument::GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="35736-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="35736-103">Возвращает длину внедренного источника в байтах.</span><span class="sxs-lookup"><span data-stu-id="35736-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35736-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35736-104">Syntax</span></span>  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35736-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="35736-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="35736-106">[out] Указатель на переменную, которая указывает длину внедренного источника, в байтах.</span><span class="sxs-lookup"><span data-stu-id="35736-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35736-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="35736-107">Return Value</span></span>  
 <span data-ttu-id="35736-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="35736-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35736-109">См. также</span><span class="sxs-lookup"><span data-stu-id="35736-109">See also</span></span>

- [<span data-ttu-id="35736-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="35736-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
