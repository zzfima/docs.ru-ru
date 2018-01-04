---
title: "Метод ISymUnmanagedReader::GetMethodByVersion"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodByVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 810cc5cda9de7c61c1b23d1574ceff19bfec3bc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="10368-102">Метод ISymUnmanagedReader::GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="10368-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="10368-103">Получает метод средства чтения символов, заданному маркеру метода и номеру версии редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="10368-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="10368-104">Номера версий начинаются с 1 и увеличивается каждый раз, когда метод изменяется в результате операции редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="10368-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10368-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10368-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10368-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="10368-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="10368-107">[in] Маркер метода.</span><span class="sxs-lookup"><span data-stu-id="10368-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="10368-108">[in] Версия метода.</span><span class="sxs-lookup"><span data-stu-id="10368-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="10368-109">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="10368-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10368-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10368-110">Return Value</span></span>  
 <span data-ttu-id="10368-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="10368-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10368-112">Требования</span><span class="sxs-lookup"><span data-stu-id="10368-112">Requirements</span></span>  
 <span data-ttu-id="10368-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="10368-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10368-114">См. также</span><span class="sxs-lookup"><span data-stu-id="10368-114">See Also</span></span>  
 [<span data-ttu-id="10368-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="10368-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
