---
title: Метод ISymUnmanagedReader2::GetSymAttributePreRemap
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
ms.openlocfilehash: 4009f8988c90ed090c0cc3d86164af347055722f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446418"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="7ce48-102">Метод ISymUnmanagedReader2::GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="7ce48-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>
<span data-ttu-id="7ce48-103">Возвращает настраиваемый атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="7ce48-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="7ce48-104">В отличие от пользовательских атрибутов метаданных эти атрибуты хранятся в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="7ce48-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ce48-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ce48-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ce48-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ce48-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="7ce48-107">окне Маркер метаданных родителя.</span><span class="sxs-lookup"><span data-stu-id="7ce48-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="7ce48-108">окне Указатель на `WCHAR`, содержащий имя.</span><span class="sxs-lookup"><span data-stu-id="7ce48-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="7ce48-109">окне `ULONG32`, указывающий размер массива `buffer`.</span><span class="sxs-lookup"><span data-stu-id="7ce48-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="7ce48-110">заполняет Указатель на `ULONG32`, который получает размер буфера, необходимый для хранения байтов атрибута.</span><span class="sxs-lookup"><span data-stu-id="7ce48-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="7ce48-111">заполняет Указатель на буфер, который получает байты атрибута.</span><span class="sxs-lookup"><span data-stu-id="7ce48-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ce48-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7ce48-112">Return Value</span></span>  
 <span data-ttu-id="7ce48-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="7ce48-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ce48-114">Требования</span><span class="sxs-lookup"><span data-stu-id="7ce48-114">Requirements</span></span>  
 <span data-ttu-id="7ce48-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="7ce48-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce48-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="7ce48-116">See also</span></span>

- [<span data-ttu-id="7ce48-117">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="7ce48-117">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
