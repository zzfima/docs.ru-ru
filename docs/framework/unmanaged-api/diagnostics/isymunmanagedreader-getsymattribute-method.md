---
title: "Метод ISymUnmanagedReader::GetSymAttribute"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetSymAttribute
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f57d2c4541945d90b1695850311928884fdc9cc5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="6684b-102">Метод ISymUnmanagedReader::GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="6684b-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="6684b-103">Получает пользовательский атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="6684b-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="6684b-104">В отличие от настраиваемых атрибутов метаданных эти настраиваемые атрибуты хранятся в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="6684b-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6684b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6684b-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6684b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6684b-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="6684b-107">[in] Токен метаданных для объекта, для которого запрашивается атрибут.</span><span class="sxs-lookup"><span data-stu-id="6684b-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="6684b-108">[in] Указатель на переменную, которая указывает извлекаемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="6684b-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="6684b-109">[in] Размер массива `buffer`.</span><span class="sxs-lookup"><span data-stu-id="6684b-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="6684b-110">[out] Указатель на переменную, которая получает длину данных атрибута.</span><span class="sxs-lookup"><span data-stu-id="6684b-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="6684b-111">[out] Указатель на переменную, которая получает данные атрибута.</span><span class="sxs-lookup"><span data-stu-id="6684b-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6684b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6684b-112">Return Value</span></span>  
 <span data-ttu-id="6684b-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки...</span><span class="sxs-lookup"><span data-stu-id="6684b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code..</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6684b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6684b-114">Requirements</span></span>  
 <span data-ttu-id="6684b-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6684b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6684b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6684b-116">See Also</span></span>  
 [<span data-ttu-id="6684b-117">ISymUnmanagedReader-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6684b-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
