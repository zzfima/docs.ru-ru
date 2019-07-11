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
ms.openlocfilehash: cfc4507557102e19d95f1b746b3a76a231882d7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736744"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="8c5b8-102">Метод ISymUnmanagedReader::UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="8c5b8-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="8c5b8-103">Обновляет существующее хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="8c5b8-104">Этот метод используется в сценариях, редактирование и продолжение для обновления хранилища символов в соответствии с изменениями исходного переносимого исполняемого (PE) файла.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c5b8-105">Вы должны указать только один из `filename` или `pIStream` параметров, не оба.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="8c5b8-106">Если `filename` указан, обновляется в хранилище символов с символами в этом файле.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="8c5b8-107">Если `pIStream` указан, хранилище будет обновлено с данными из <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5b8-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c5b8-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c5b8-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c5b8-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="8c5b8-110">[in] Имя файла, содержащего хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="8c5b8-111">[in] Файловый поток, используемый в качестве альтернативы для `filename` параметра.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c5b8-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8c5b8-112">Return Value</span></span>  
 <span data-ttu-id="8c5b8-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c5b8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8c5b8-114">Requirements</span></span>  
 <span data-ttu-id="8c5b8-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8c5b8-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5b8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8c5b8-116">See also</span></span>

- [<span data-ttu-id="8c5b8-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="8c5b8-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
