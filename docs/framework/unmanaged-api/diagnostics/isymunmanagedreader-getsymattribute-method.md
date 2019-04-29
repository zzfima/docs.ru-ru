---
title: Метод ISymUnmanagedReader::GetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89831261c5da156343cb098ace715495ddafccaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968757"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="bee93-102">Метод ISymUnmanagedReader::GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="bee93-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="bee93-103">Получает настраиваемый атрибут, в зависимости от его имени.</span><span class="sxs-lookup"><span data-stu-id="bee93-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="bee93-104">В отличие от настраиваемых атрибутов метаданных эти настраиваемые атрибуты хранятся в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="bee93-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bee93-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bee93-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bee93-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bee93-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="bee93-107">[in] Токен метаданных для объекта, для которого запрашивается этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="bee93-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="bee93-108">[in] Указатель на переменную, которая указывает извлекаемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="bee93-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="bee93-109">[in] Размер массива `buffer`.</span><span class="sxs-lookup"><span data-stu-id="bee93-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="bee93-110">[out] Указатель на переменную, которая получает длину данных атрибута.</span><span class="sxs-lookup"><span data-stu-id="bee93-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="bee93-111">[out] Указатель на переменную, которая получает данные атрибута.</span><span class="sxs-lookup"><span data-stu-id="bee93-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bee93-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bee93-112">Return Value</span></span>  
 <span data-ttu-id="bee93-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="bee93-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bee93-114">Требования</span><span class="sxs-lookup"><span data-stu-id="bee93-114">Requirements</span></span>  
 <span data-ttu-id="bee93-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bee93-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bee93-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bee93-116">See also</span></span>

- [<span data-ttu-id="bee93-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="bee93-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
