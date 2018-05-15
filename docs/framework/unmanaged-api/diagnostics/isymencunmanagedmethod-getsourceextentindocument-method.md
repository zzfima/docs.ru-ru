---
title: Метод ISymENCUnmanagedMethod::GetSourceExtentInDocument
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc3a986326f9b47194558ca86bcbeabb61dbaeb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="3a2c3-102">Метод ISymENCUnmanagedMethod::GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="3a2c3-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="3a2c3-103">Возвращает наименьшую начальную или наибольшую конечную строку метода в определенном документе.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a2c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a2c3-104">Syntax</span></span>  
  
```  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a2c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a2c3-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="3a2c3-106">[in] Указатель на документ.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="3a2c3-107">[out] Указатель на `ULONG32` , получающий начальной строки.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="3a2c3-108">[out] Указатель на `ULONG32` , получающий конца строки.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a2c3-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3a2c3-109">Return Value</span></span>  
 <span data-ttu-id="3a2c3-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a2c3-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3a2c3-111">Requirements</span></span>  
 <span data-ttu-id="3a2c3-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3a2c3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a2c3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3a2c3-113">See Also</span></span>  
 [<span data-ttu-id="3a2c3-114">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="3a2c3-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
