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
ms.openlocfilehash: 2063856389b122b150a2d2744169a4a567592287
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446448"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="354b0-102">Метод ISymUnmanagedReader2::GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="354b0-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="354b0-103">Возвращает метод чтения символов по заданному маркеру метода и номеру версии "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="354b0-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="354b0-104">Номера версий начинаются с 1 и увеличиваются каждый раз при изменении метода в результате операции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="354b0-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="354b0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="354b0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="354b0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="354b0-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="354b0-107">окне Токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="354b0-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="354b0-108">окне Версия метода.</span><span class="sxs-lookup"><span data-stu-id="354b0-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="354b0-109">заполняет Указатель на возвращаемый интерфейс [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="354b0-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="354b0-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="354b0-110">Return Value</span></span>  
 <span data-ttu-id="354b0-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="354b0-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="354b0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="354b0-112">Requirements</span></span>  
 <span data-ttu-id="354b0-113">**Заголовок:** Корсим. idl.</span><span class="sxs-lookup"><span data-stu-id="354b0-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="354b0-114">Корсим. h</span><span class="sxs-lookup"><span data-stu-id="354b0-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="354b0-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="354b0-115">See also</span></span>

- [<span data-ttu-id="354b0-116">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="354b0-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
