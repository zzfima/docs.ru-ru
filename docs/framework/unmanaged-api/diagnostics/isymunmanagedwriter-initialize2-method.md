---
title: Метод ISymUnmanagedWriter::Initialize2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
ms.openlocfilehash: 041df959139a0be77f40d6aa5655ff15f93fb26f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427945"
---
# <a name="isymunmanagedwriterinitialize2-method"></a><span data-ttu-id="83d50-102">Метод ISymUnmanagedWriter::Initialize2</span><span class="sxs-lookup"><span data-stu-id="83d50-102">ISymUnmanagedWriter::Initialize2 Method</span></span>
<span data-ttu-id="83d50-103">Задает интерфейс передатчика метаданных, с которым будет связан этот модуль записи, и задает имя выходного файла, в который будут записываться отладочные символы.</span><span class="sxs-lookup"><span data-stu-id="83d50-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span> <span data-ttu-id="83d50-104">Этот метод также позволяет задать конечное расположение файла базы данных программы (PDB).</span><span class="sxs-lookup"><span data-stu-id="83d50-104">This method also lets you set the final location of the program database (PDB) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d50-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83d50-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83d50-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="83d50-106">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="83d50-107">окне Указатель на интерфейс передатчика метаданных.</span><span class="sxs-lookup"><span data-stu-id="83d50-107">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `tempfilename`  
 <span data-ttu-id="83d50-108">окне Указатель на `WCHAR`, содержащий имя файла, в который записываются отладочные символы.</span><span class="sxs-lookup"><span data-stu-id="83d50-108">[in] A pointer to a `WCHAR` that contains the file name to which the debugging symbols are written.</span></span> <span data-ttu-id="83d50-109">Если имя файла задано для модуля записи, который не использует имена файлов, этот параметр пропускается.</span><span class="sxs-lookup"><span data-stu-id="83d50-109">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="83d50-110">окне Если указан, средство записи символов создает символы в заданном <xref:System.Runtime.InteropServices.ComTypes.IStream>, а не в файле, указанном в параметре `filename`.</span><span class="sxs-lookup"><span data-stu-id="83d50-110">[in] If specified, the symbol writer emits the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="83d50-111">Параметр `pIStream` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="83d50-111">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="83d50-112">[in] `true`, если это полная перестроение; `false`, если это инкрементная компиляция.</span><span class="sxs-lookup"><span data-stu-id="83d50-112">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
 `finalfilename`  
 <span data-ttu-id="83d50-113">окне Указатель на `WCHAR`, который является строкой пути к окончательному расположению PDB-файла.</span><span class="sxs-lookup"><span data-stu-id="83d50-113">[in] A pointer to a `WCHAR` that is the path string to the final location of the PDB file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83d50-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83d50-114">Return Value</span></span>  
 <span data-ttu-id="83d50-115">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="83d50-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83d50-116">Требования</span><span class="sxs-lookup"><span data-stu-id="83d50-116">Requirements</span></span>  
 <span data-ttu-id="83d50-117">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="83d50-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d50-118">См. также</span><span class="sxs-lookup"><span data-stu-id="83d50-118">See also</span></span>

- [<span data-ttu-id="83d50-119">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="83d50-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="83d50-120">Метод Initialize</span><span class="sxs-lookup"><span data-stu-id="83d50-120">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
