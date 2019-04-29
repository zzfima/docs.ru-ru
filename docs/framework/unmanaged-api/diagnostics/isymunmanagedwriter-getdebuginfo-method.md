---
title: Метод ISymUnmanagedWriter::GetDebugInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 41d96c6d2024dbc3cab669f2dba2f99faef89f4b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701298"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="83fb3-102">Метод ISymUnmanagedWriter::GetDebugInfo</span><span class="sxs-lookup"><span data-stu-id="83fb3-102">ISymUnmanagedWriter::GetDebugInfo Method</span></span>
<span data-ttu-id="83fb3-103">Возвращает информацию, необходимую для компилятора, чтобы написать запись каталога отладки в заголовок переносимого исполняемого (PE) файла.</span><span class="sxs-lookup"><span data-stu-id="83fb3-103">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="83fb3-104">Модуль записи символов заполнения всех полей, за исключением `TimeDateStamp` и `PointerToRawData`.</span><span class="sxs-lookup"><span data-stu-id="83fb3-104">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="83fb3-105">(Компилятор отвечает за правильную настройку этих полей.)</span><span class="sxs-lookup"><span data-stu-id="83fb3-105">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="83fb3-106">Компилятор должен вызывать этот метод, порождаемого большой двоичный объект данных к PE-файлу, задайте `PointerToRawData` в IMAGE_DEBUG_DIRECTORY пункты порожденную данных и запись IMAGE_DEBUG_DIRECTORY PE-файл.</span><span class="sxs-lookup"><span data-stu-id="83fb3-106">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="83fb3-107">Компилятор также следует задать `TimeDateStamp` равным `TimeDateStamp` создаваемого PE-файла.</span><span class="sxs-lookup"><span data-stu-id="83fb3-107">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83fb3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83fb3-108">Syntax</span></span>  
  
```  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83fb3-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="83fb3-109">Parameters</span></span>  
 `pIDD`  
 <span data-ttu-id="83fb3-110">[in, out] Указатель на IMAGE_DEBUG_DIRECTORY, заполняемой интерфейс записи символов.</span><span class="sxs-lookup"><span data-stu-id="83fb3-110">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="83fb3-111">[in] Объект `DWORD` , содержащий размер данных отладки.</span><span class="sxs-lookup"><span data-stu-id="83fb3-111">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="83fb3-112">[out] Указатель на `DWORD` , принимает размер буфера, требуемого для хранения данных отладки.</span><span class="sxs-lookup"><span data-stu-id="83fb3-112">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="83fb3-113">[out] Указатель на буфер, достаточно велик для хранения данных в хранилище символов отладки.</span><span class="sxs-lookup"><span data-stu-id="83fb3-113">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83fb3-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83fb3-114">Return Value</span></span>  
 <span data-ttu-id="83fb3-115">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="83fb3-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83fb3-116">Требования</span><span class="sxs-lookup"><span data-stu-id="83fb3-116">Requirements</span></span>  
 <span data-ttu-id="83fb3-117">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="83fb3-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83fb3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="83fb3-118">See also</span></span>

- [<span data-ttu-id="83fb3-119">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="83fb3-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
