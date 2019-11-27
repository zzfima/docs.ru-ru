---
title: Метод ISymUnmanagedReader2::GetMethodsInDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
ms.openlocfilehash: 70c1d87ae32fb70f8d9f6e32b527394022459526
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446433"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="ec908-102">Метод ISymUnmanagedReader2::GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="ec908-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="ec908-103">Возвращает каждый метод, имеющий сведения о строке в указанном документе.</span><span class="sxs-lookup"><span data-stu-id="ec908-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec908-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec908-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec908-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec908-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="ec908-106">окне Указатель на документ.</span><span class="sxs-lookup"><span data-stu-id="ec908-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="ec908-107">окне `ULONG32`, указывающий размер массива `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="ec908-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="ec908-108">заполняет Указатель на `ULONG32`, который получает размер буфера, необходимый для хранения методов.</span><span class="sxs-lookup"><span data-stu-id="ec908-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="ec908-109">заполняет Указатель на буфер, который получает методы.</span><span class="sxs-lookup"><span data-stu-id="ec908-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec908-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ec908-110">Return Value</span></span>  
 <span data-ttu-id="ec908-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="ec908-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec908-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ec908-112">Requirements</span></span>  
 <span data-ttu-id="ec908-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="ec908-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec908-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ec908-114">See also</span></span>

- [<span data-ttu-id="ec908-115">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="ec908-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
