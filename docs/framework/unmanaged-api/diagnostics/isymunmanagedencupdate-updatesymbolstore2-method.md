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
ms.openlocfilehash: 9d2c641f011c55ee726e319cb581705e334c840d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774678"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="e5073-102">Метод ISymUnmanagedENCUpdate::UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="e5073-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="e5073-103">Позволяет компилятору пропускать функции, которые не были изменены из потока базы данных (PDB) программы, предоставляемые данные строки соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="e5073-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="e5073-104">Правильные сведения строки можно определить с помощью старых сведений строки PDB и одного разностного для всех строк в функции.</span><span class="sxs-lookup"><span data-stu-id="e5073-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5073-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5073-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5073-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5073-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="e5073-107">[in] Указатель на [IStream](/windows/desktop/api/objidl/nn-objidl-istream) , содержащий сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="e5073-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="e5073-108">[in] Указатель на [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) структуру, содержащую строки, которые были изменены.</span><span class="sxs-lookup"><span data-stu-id="e5073-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="e5073-109">[in] Объект `ULONG` , представляющий количество строк, которые были изменены.</span><span class="sxs-lookup"><span data-stu-id="e5073-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5073-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e5073-110">Return Value</span></span>  
 <span data-ttu-id="e5073-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="e5073-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5073-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e5073-112">Requirements</span></span>  
 <span data-ttu-id="e5073-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e5073-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5073-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e5073-114">See also</span></span>

- [<span data-ttu-id="e5073-115">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="e5073-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
