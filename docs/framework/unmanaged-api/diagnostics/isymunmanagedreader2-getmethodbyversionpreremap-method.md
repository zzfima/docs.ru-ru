---
title: Метод ISymUnmanagedReader2::GetMethodByVersionPreRemap
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bcd200b7fa431f193dd202c3c2a690aa22ec8e32
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986262"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="b9a92-102">Метод ISymUnmanagedReader2::GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="b9a92-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="b9a92-103">Получает метода средства чтения символов, получив токен метода и номеру версии, изменить и продолжить.</span><span class="sxs-lookup"><span data-stu-id="b9a92-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="b9a92-104">Номера версий начинаются с 1 и увеличивается каждый раз, когда метод изменяется в результате операции изменить и продолжить.</span><span class="sxs-lookup"><span data-stu-id="b9a92-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9a92-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9a92-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9a92-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9a92-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="b9a92-107">[in] Токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="b9a92-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="b9a92-108">[in] Версия метода.</span><span class="sxs-lookup"><span data-stu-id="b9a92-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="b9a92-109">[out] Указатель на возвращенный [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b9a92-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9a92-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b9a92-110">Return Value</span></span>  
 <span data-ttu-id="b9a92-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b9a92-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9a92-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b9a92-112">Requirements</span></span>  
 <span data-ttu-id="b9a92-113">**Заголовок.** CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="b9a92-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="b9a92-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b9a92-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a92-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b9a92-115">See also</span></span>

- [<span data-ttu-id="b9a92-116">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="b9a92-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
