---
title: Метод ISymUnmanagedMethod::GetOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
ms.openlocfilehash: f7993ebc15f95df97a9b45523717f318d8c435ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448948"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="1ba94-102">Метод ISymUnmanagedMethod::GetOffset</span><span class="sxs-lookup"><span data-stu-id="1ba94-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="1ba94-103">Возвращает смещение в этом методе, соответствующее заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="1ba94-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba94-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ba94-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ba94-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ba94-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="1ba94-106">окне Указатель на документ, для которого запрашивается смещение.</span><span class="sxs-lookup"><span data-stu-id="1ba94-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="1ba94-107">окне Строка документа, для которой запрашивается смещение.</span><span class="sxs-lookup"><span data-stu-id="1ba94-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="1ba94-108">окне Столбец документа, для которого запрашивается смещение.</span><span class="sxs-lookup"><span data-stu-id="1ba94-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1ba94-109">заполняет Указатель на `ULONG32`, который получает смещения.</span><span class="sxs-lookup"><span data-stu-id="1ba94-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ba94-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1ba94-110">Return Value</span></span>  
 <span data-ttu-id="1ba94-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="1ba94-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ba94-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1ba94-112">Requirements</span></span>  
 <span data-ttu-id="1ba94-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="1ba94-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba94-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ba94-114">See also</span></span>

- [<span data-ttu-id="1ba94-115">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="1ba94-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
