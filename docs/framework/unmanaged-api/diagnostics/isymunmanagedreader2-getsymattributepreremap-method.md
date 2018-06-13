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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 326f970f53293b74bbf8c5e77830f3f6ce1b73ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427041"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="b6b5b-102">Метод ISymUnmanagedReader2::GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="b6b5b-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>
<span data-ttu-id="b6b5b-103">Получает пользовательский атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="b6b5b-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="b6b5b-104">В отличие от настраиваемых атрибутов метаданных эти атрибуты хранятся в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="b6b5b-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6b5b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6b5b-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6b5b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6b5b-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="b6b5b-107">[in] Токен метаданных родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="b6b5b-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="b6b5b-108">[in] Указатель на `WCHAR` , содержащее имя.</span><span class="sxs-lookup"><span data-stu-id="b6b5b-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="b6b5b-109">[in] Объект `ULONG32` указывает размер `buffer` массива.</span><span class="sxs-lookup"><span data-stu-id="b6b5b-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="b6b5b-110">[out] Указатель на `ULONG32` , получающий размер буфера, который должен содержать атрибут байт.</span><span class="sxs-lookup"><span data-stu-id="b6b5b-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="b6b5b-111">[out] Указатель на буфер, в который помещаются байты атрибута.</span><span class="sxs-lookup"><span data-stu-id="b6b5b-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6b5b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b6b5b-112">Return Value</span></span>  
 <span data-ttu-id="b6b5b-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b6b5b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6b5b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b6b5b-114">Requirements</span></span>  
 <span data-ttu-id="b6b5b-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b6b5b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b5b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b6b5b-116">See Also</span></span>  
 [<span data-ttu-id="b6b5b-117">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="b6b5b-117">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
