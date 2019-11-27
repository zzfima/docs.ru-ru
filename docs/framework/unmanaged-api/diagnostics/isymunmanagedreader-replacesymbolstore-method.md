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
ms.openlocfilehash: 60c3537a80c39f758f46e6f2f0a5f2bcd27350b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445737"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="621e4-102">Метод ISymUnmanagedReader::ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="621e4-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="621e4-103">Заменяет имеющееся хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="621e4-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="621e4-104">Этот метод аналогичен методу [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) , за исключением того, что данная Дельта действует как полная замена, а не как обновление.</span><span class="sxs-lookup"><span data-stu-id="621e4-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="621e4-105">Необходимо указать только один из параметров `filename` или `pIStream`, но не оба.</span><span class="sxs-lookup"><span data-stu-id="621e4-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="621e4-106">Если указан `filename`, хранилище символов будет обновлено символами из этого файла.</span><span class="sxs-lookup"><span data-stu-id="621e4-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="621e4-107">Если указано `pIStream`, хранилище будет обновлено данными из <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="621e4-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="621e4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="621e4-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="621e4-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="621e4-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="621e4-110">окне Имя файла, содержащего хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="621e4-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="621e4-111">окне Файловый поток, используемый в качестве альтернативы параметру `filename`.</span><span class="sxs-lookup"><span data-stu-id="621e4-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="621e4-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="621e4-112">Return Value</span></span>  
 <span data-ttu-id="621e4-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="621e4-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="621e4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="621e4-114">Requirements</span></span>  
 <span data-ttu-id="621e4-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="621e4-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="621e4-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="621e4-116">See also</span></span>

- [<span data-ttu-id="621e4-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="621e4-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
