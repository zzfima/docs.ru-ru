---
title: Метод ISymUnmanagedReader::UpdateSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d84d4fccb2cb4e500f07f6bfbfb93b8c7b81f5d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939006"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="06b6f-102">Метод ISymUnmanagedReader::UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="06b6f-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="06b6f-103">Обновляет существующее хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="06b6f-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="06b6f-104">Этот метод используется в сценариях "изменить и продолжить" для обновления хранилища символов в соответствии с разностью с исходным переносимым исполняемым файлом (PE).</span><span class="sxs-lookup"><span data-stu-id="06b6f-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="06b6f-105">Необходимо указать только один из `filename` параметров или `pIStream` , но не оба.</span><span class="sxs-lookup"><span data-stu-id="06b6f-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="06b6f-106">Если `filename` указан параметр, хранилище символов будет обновлено символами из этого файла.</span><span class="sxs-lookup"><span data-stu-id="06b6f-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="06b6f-107">Если `pIStream` указан параметр, хранилище будет обновляться данными <xref:System.Runtime.InteropServices.ComTypes.IStream>из.</span><span class="sxs-lookup"><span data-stu-id="06b6f-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b6f-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06b6f-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06b6f-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="06b6f-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="06b6f-110">окне Имя файла, содержащего хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="06b6f-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="06b6f-111">окне Файловый поток, используемый в качестве альтернативы `filename` параметру.</span><span class="sxs-lookup"><span data-stu-id="06b6f-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06b6f-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="06b6f-112">Return Value</span></span>  
 <span data-ttu-id="06b6f-113">Значение S_OK, если метод выполнен. в противном случае — E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="06b6f-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06b6f-114">Требования</span><span class="sxs-lookup"><span data-stu-id="06b6f-114">Requirements</span></span>  
 <span data-ttu-id="06b6f-115">**Заголовок.** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="06b6f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b6f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="06b6f-116">See also</span></span>

- [<span data-ttu-id="06b6f-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="06b6f-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
