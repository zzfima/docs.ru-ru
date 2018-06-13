---
title: Метод ISymUnmanagedDocument::GetCheckSumAlgorithmId
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c815b256ebdab82a57f921a5df016a1552f6d052
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424356"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="73b8e-102">Метод ISymUnmanagedDocument::GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="73b8e-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="73b8e-103">Возвращает идентификатор алгоритма подсчета контрольной суммы или возвращает идентификатор GUID из нулей, если контрольная сумма отсутствует.</span><span class="sxs-lookup"><span data-stu-id="73b8e-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73b8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73b8e-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73b8e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="73b8e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="73b8e-106">[out] Указатель на переменную, которая получает идентификатор алгоритма подсчета контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="73b8e-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73b8e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="73b8e-107">Return Value</span></span>  
 <span data-ttu-id="73b8e-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="73b8e-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b8e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="73b8e-109">See Also</span></span>  
 [<span data-ttu-id="73b8e-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="73b8e-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
