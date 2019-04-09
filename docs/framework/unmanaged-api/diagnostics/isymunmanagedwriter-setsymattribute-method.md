---
title: Метод ISymUnmanagedWriter::SetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8ffcc3a079e7e9a9d69622dc6666bb0e7641d4e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155471"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="c12fa-102">Метод ISymUnmanagedWriter::SetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="c12fa-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="c12fa-103">Определяет настраиваемый атрибут, в зависимости от его имени.</span><span class="sxs-lookup"><span data-stu-id="c12fa-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="c12fa-104">Эти атрибуты хранятся в хранилище символов, в отличие от настраиваемых атрибутов метаданных.</span><span class="sxs-lookup"><span data-stu-id="c12fa-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c12fa-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c12fa-105">Syntax</span></span>  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c12fa-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c12fa-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="c12fa-107">[in] Токен метаданных, для которого определен атрибут.</span><span class="sxs-lookup"><span data-stu-id="c12fa-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="c12fa-108">[in] Указатель на `WCHAR` , содержащий имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="c12fa-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="c12fa-109">[in] Объект `ULONG32` указывает размер `data` массива.</span><span class="sxs-lookup"><span data-stu-id="c12fa-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="c12fa-110">[in] Значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="c12fa-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c12fa-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c12fa-111">Return Value</span></span>  
 <span data-ttu-id="c12fa-112">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="c12fa-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c12fa-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c12fa-113">Requirements</span></span>  
 <span data-ttu-id="c12fa-114">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c12fa-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c12fa-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c12fa-115">See also</span></span>

- [<span data-ttu-id="c12fa-116">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="c12fa-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
