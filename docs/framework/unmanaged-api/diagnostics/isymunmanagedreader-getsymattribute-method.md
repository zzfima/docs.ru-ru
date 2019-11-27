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
ms.openlocfilehash: 7f04b5c100f1fd9c44e671b883fe469b16d33fa6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440137"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="108cb-102">Метод ISymUnmanagedReader::GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="108cb-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="108cb-103">Возвращает настраиваемый атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="108cb-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="108cb-104">В отличие от пользовательских атрибутов метаданных эти пользовательские атрибуты хранятся в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="108cb-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108cb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="108cb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="108cb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="108cb-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="108cb-107">окне Токен метаданных для объекта, для которого запрашивается атрибут.</span><span class="sxs-lookup"><span data-stu-id="108cb-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="108cb-108">окне Указатель на переменную, которая указывает извлекаемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="108cb-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="108cb-109">[in] Размер массива `buffer`.</span><span class="sxs-lookup"><span data-stu-id="108cb-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="108cb-110">заполняет Указатель на переменную, которая получает длину данных атрибута.</span><span class="sxs-lookup"><span data-stu-id="108cb-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="108cb-111">заполняет Указатель на переменную, которая получает данные атрибута.</span><span class="sxs-lookup"><span data-stu-id="108cb-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="108cb-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="108cb-112">Return Value</span></span>  
 <span data-ttu-id="108cb-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="108cb-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108cb-114">Требования</span><span class="sxs-lookup"><span data-stu-id="108cb-114">Requirements</span></span>  
 <span data-ttu-id="108cb-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="108cb-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="108cb-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="108cb-116">See also</span></span>

- [<span data-ttu-id="108cb-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="108cb-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
