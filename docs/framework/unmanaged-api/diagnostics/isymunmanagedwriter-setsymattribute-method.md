---
title: "Метод ISymUnmanagedWriter::SetSymAttribute"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetSymAttribute
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c59c3c8ec4534f0a7587d4fdb772683715363066
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="793df-102">Метод ISymUnmanagedWriter::SetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="793df-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="793df-103">Определяет настраиваемый атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="793df-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="793df-104">Эти атрибуты хранятся в хранилище символов, в отличие от настраиваемых атрибутов метаданных.</span><span class="sxs-lookup"><span data-stu-id="793df-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="793df-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="793df-105">Syntax</span></span>  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="793df-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="793df-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="793df-107">[in] Токен метаданных, для которого определен атрибут.</span><span class="sxs-lookup"><span data-stu-id="793df-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="793df-108">[in] Указатель на `WCHAR` , содержащий имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="793df-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="793df-109">[in] Объект `ULONG32` указывает размер `data` массива.</span><span class="sxs-lookup"><span data-stu-id="793df-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="793df-110">[in] Значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="793df-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="793df-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="793df-111">Return Value</span></span>  
 <span data-ttu-id="793df-112">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="793df-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="793df-113">Требования</span><span class="sxs-lookup"><span data-stu-id="793df-113">Requirements</span></span>  
 <span data-ttu-id="793df-114">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="793df-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="793df-115">См. также</span><span class="sxs-lookup"><span data-stu-id="793df-115">See Also</span></span>  
 [<span data-ttu-id="793df-116">ISymUnmanagedWriter-интерфейс</span><span class="sxs-lookup"><span data-stu-id="793df-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
