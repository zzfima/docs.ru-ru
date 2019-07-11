---
title: Метод ISymUnmanagedReader::ReplaceSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 525ec4828fb942aeb447940ea68a523cd7c69140
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736727"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="31063-102">Метод ISymUnmanagedReader::ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="31063-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="31063-103">Заменяет имеющееся хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="31063-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="31063-104">Этот метод аналогичен методу [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) метода, за исключением того, что данная разность действует как полная замена, а не для обновления.</span><span class="sxs-lookup"><span data-stu-id="31063-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31063-105">Вы должны указать только один из `filename` или `pIStream` параметров, не оба.</span><span class="sxs-lookup"><span data-stu-id="31063-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="31063-106">Если `filename` указан, обновляется в хранилище символов с символами в этом файле.</span><span class="sxs-lookup"><span data-stu-id="31063-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="31063-107">Если `pIStream` указан, хранилище будет обновлено с данными из <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="31063-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31063-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31063-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31063-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="31063-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="31063-110">[in] Имя файла, содержащего хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="31063-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="31063-111">[in] Файловый поток, используемый в качестве альтернативы для `filename` параметра.</span><span class="sxs-lookup"><span data-stu-id="31063-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31063-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="31063-112">Return Value</span></span>  
 <span data-ttu-id="31063-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="31063-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31063-114">Требования</span><span class="sxs-lookup"><span data-stu-id="31063-114">Requirements</span></span>  
 <span data-ttu-id="31063-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="31063-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31063-116">См. также</span><span class="sxs-lookup"><span data-stu-id="31063-116">See also</span></span>

- [<span data-ttu-id="31063-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="31063-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
