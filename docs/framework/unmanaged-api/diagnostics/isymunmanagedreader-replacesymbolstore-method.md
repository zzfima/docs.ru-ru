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
ms.openlocfilehash: 8721f7c30061fbfd4a761bed090b761762c3c13c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939026"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="8a6e6-102">Метод ISymUnmanagedReader::ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="8a6e6-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="8a6e6-103">Заменяет имеющееся хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="8a6e6-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="8a6e6-104">Этот метод аналогичен методу [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) , за исключением того, что данная Дельта действует как полная замена, а не как обновление.</span><span class="sxs-lookup"><span data-stu-id="8a6e6-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a6e6-105">Необходимо указать только один из `filename` параметров или `pIStream` , но не оба.</span><span class="sxs-lookup"><span data-stu-id="8a6e6-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="8a6e6-106">Если `filename` указан параметр, хранилище символов будет обновлено символами из этого файла.</span><span class="sxs-lookup"><span data-stu-id="8a6e6-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="8a6e6-107">Если `pIStream` указан параметр, хранилище будет обновляться данными <xref:System.Runtime.InteropServices.ComTypes.IStream>из.</span><span class="sxs-lookup"><span data-stu-id="8a6e6-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a6e6-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a6e6-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a6e6-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a6e6-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="8a6e6-110">окне Имя файла, содержащего хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="8a6e6-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="8a6e6-111">окне Файловый поток, используемый в качестве альтернативы `filename` параметру.</span><span class="sxs-lookup"><span data-stu-id="8a6e6-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a6e6-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8a6e6-112">Return Value</span></span>  
 <span data-ttu-id="8a6e6-113">Значение S_OK, если метод выполнен. в противном случае — E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="8a6e6-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a6e6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8a6e6-114">Requirements</span></span>  
 <span data-ttu-id="8a6e6-115">**Заголовок.** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="8a6e6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a6e6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8a6e6-116">See also</span></span>

- [<span data-ttu-id="8a6e6-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="8a6e6-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
