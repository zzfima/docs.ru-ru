---
title: "Метод ISymUnmanagedReader::GetMethodVersion"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 713b8a89c9519abe407ac1d68adb2552cd012b1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="2d22f-102">Метод ISymUnmanagedReader::GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="2d22f-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="2d22f-103">Получает версию метода.</span><span class="sxs-lookup"><span data-stu-id="2d22f-103">Gets the method version.</span></span> <span data-ttu-id="2d22f-104">Версия метода начинается с 1 и увеличивается каждый раз, когда метод компилируется.</span><span class="sxs-lookup"><span data-stu-id="2d22f-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="2d22f-105">Перекомпиляция может происходить без изменений в метод.</span><span class="sxs-lookup"><span data-stu-id="2d22f-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d22f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d22f-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d22f-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="2d22f-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="2d22f-108">[in] Метод, для которого требуется получить версию.</span><span class="sxs-lookup"><span data-stu-id="2d22f-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="2d22f-109">[out] Указатель на переменную, которая получает версию метода.</span><span class="sxs-lookup"><span data-stu-id="2d22f-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d22f-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2d22f-110">Return Value</span></span>  
 <span data-ttu-id="2d22f-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="2d22f-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d22f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2d22f-112">Requirements</span></span>  
 <span data-ttu-id="2d22f-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2d22f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d22f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2d22f-114">See Also</span></span>  
 [<span data-ttu-id="2d22f-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="2d22f-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
