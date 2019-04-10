---
title: Метод ISymUnmanagedWriter::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 417cf623948d16147f9a1242d714f4df1311a314
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212054"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="9f19c-102">Метод ISymUnmanagedWriter::Initialize</span><span class="sxs-lookup"><span data-stu-id="9f19c-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="9f19c-103">Задает интерфейс включения метаданных, с которым будет связан этот модуль записи и задает имя выходного файла, в который записываются символы отладки.</span><span class="sxs-lookup"><span data-stu-id="9f19c-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="9f19c-104">Этот метод может вызываться только один раз и должен вызываться до всех остальных методов модуля записи.</span><span class="sxs-lookup"><span data-stu-id="9f19c-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="9f19c-105">Некоторые модули записи может потребоваться имя файла.</span><span class="sxs-lookup"><span data-stu-id="9f19c-105">Some writers may require a file name.</span></span> <span data-ttu-id="9f19c-106">Тем не менее всегда можно передать имя файла для этого метода без любого отрицательного влияния на средства записи, не используйте имя файла.</span><span class="sxs-lookup"><span data-stu-id="9f19c-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f19c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f19c-107">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f19c-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f19c-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="9f19c-109">[in] Указатель на интерфейс включения метаданных.</span><span class="sxs-lookup"><span data-stu-id="9f19c-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="9f19c-110">[in] Имя файла, в который записываются символы отладки.</span><span class="sxs-lookup"><span data-stu-id="9f19c-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="9f19c-111">Если имя файла задано для модуля записи, который не использует имена файлов, этот параметр пропускается.</span><span class="sxs-lookup"><span data-stu-id="9f19c-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="9f19c-112">[in] Если указан, модуль записи символов будет выдавать символы в заданной <xref:System.Runtime.InteropServices.ComTypes.IStream> , а не файл, указанный в `filename` параметра.</span><span class="sxs-lookup"><span data-stu-id="9f19c-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="9f19c-113">Параметр `pIStream` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9f19c-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="9f19c-114">[in] `true` Если это полное перестроение; `false` Если это добавочная компиляция.</span><span class="sxs-lookup"><span data-stu-id="9f19c-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f19c-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9f19c-115">Return Value</span></span>  
 <span data-ttu-id="9f19c-116">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="9f19c-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f19c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="9f19c-117">Requirements</span></span>  
 <span data-ttu-id="9f19c-118">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9f19c-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f19c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9f19c-119">See also</span></span>

- [<span data-ttu-id="9f19c-120">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="9f19c-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="9f19c-121">Метод Initialize2</span><span class="sxs-lookup"><span data-stu-id="9f19c-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
