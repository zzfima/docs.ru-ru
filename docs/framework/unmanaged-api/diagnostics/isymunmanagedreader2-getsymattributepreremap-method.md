---
title: "Метод ISymUnmanagedReader2::GetSymAttributePreRemap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetSymAttributePreRemap
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a9e2304e746578fbe0e7a5c4d1b0ef1f1c8a1b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="bf37d-102">Метод ISymUnmanagedReader2::GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="bf37d-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>
<span data-ttu-id="bf37d-103">Получает пользовательский атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="bf37d-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="bf37d-104">В отличие от настраиваемых атрибутов метаданных эти атрибуты хранятся в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="bf37d-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf37d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf37d-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf37d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf37d-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="bf37d-107">[in] Токен метаданных родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="bf37d-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="bf37d-108">[in] Указатель на `WCHAR` , содержащее имя.</span><span class="sxs-lookup"><span data-stu-id="bf37d-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="bf37d-109">[in] Объект `ULONG32` указывает размер `buffer` массива.</span><span class="sxs-lookup"><span data-stu-id="bf37d-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="bf37d-110">[out] Указатель на `ULONG32` , получающий размер буфера, который должен содержать атрибут байт.</span><span class="sxs-lookup"><span data-stu-id="bf37d-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="bf37d-111">[out] Указатель на буфер, в который помещаются байты атрибута.</span><span class="sxs-lookup"><span data-stu-id="bf37d-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf37d-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bf37d-112">Return Value</span></span>  
 <span data-ttu-id="bf37d-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="bf37d-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf37d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="bf37d-114">Requirements</span></span>  
 <span data-ttu-id="bf37d-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bf37d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf37d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bf37d-116">See Also</span></span>  
 [<span data-ttu-id="bf37d-117">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="bf37d-117">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
