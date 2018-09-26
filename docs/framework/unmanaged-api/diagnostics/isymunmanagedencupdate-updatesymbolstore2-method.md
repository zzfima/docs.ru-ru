---
title: Метод ISymUnmanagedENCUpdate::UpdateSymbolStore2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78d9e27299c9d7ed7d6cb9b09dd659ba081c5fde
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47204973"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="4b429-102">Метод ISymUnmanagedENCUpdate::UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="4b429-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="4b429-103">Позволяет компилятору пропускать функции, которые не были изменены из потока базы данных (PDB) программы, предоставляемые данные строки соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="4b429-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="4b429-104">Правильные сведения строки можно определить с помощью старых сведений строки PDB и одного разностного для всех строк в функции.</span><span class="sxs-lookup"><span data-stu-id="4b429-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b429-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b429-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b429-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b429-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="4b429-107">[in] Указатель на [IStream](/windows/desktop/api/objidl/nn-objidl-istream) , содержащий сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="4b429-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="4b429-108">[in] Указатель на [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) структуру, содержащую строки, которые были изменены.</span><span class="sxs-lookup"><span data-stu-id="4b429-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="4b429-109">[in] Объект `ULONG` , представляющий количество строк, которые были изменены.</span><span class="sxs-lookup"><span data-stu-id="4b429-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b429-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4b429-110">Return Value</span></span>  
 <span data-ttu-id="4b429-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4b429-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b429-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4b429-112">Requirements</span></span>  
 <span data-ttu-id="4b429-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4b429-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b429-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4b429-114">See Also</span></span>  
 [<span data-ttu-id="4b429-115">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="4b429-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
