---
title: Метод GetWin32ResBlob
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b26f08548ac964fae2f4d64db50167add327eb2d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777372"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="c17dc-102">Метод GetWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="c17dc-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="c17dc-103">Извлекает BLOB-объект ресурса Win32.</span><span class="sxs-lookup"><span data-stu-id="c17dc-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="c17dc-104">Вызовите этот метод после установки параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="c17dc-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c17dc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c17dc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c17dc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c17dc-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c17dc-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="c17dc-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="c17dc-108">Токен файла, используемый для получения имени файла, используемого при создании ресурса версии Win32</span><span class="sxs-lookup"><span data-stu-id="c17dc-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="c17dc-109">Значение TRUE, если файл является библиотекой DLL, и false для EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="c17dc-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="c17dc-110">Необязательный значок для вставки в большой двоичный объект ресурса.</span><span class="sxs-lookup"><span data-stu-id="c17dc-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="c17dc-111">Получает большой двоичный объект ресурса.</span><span class="sxs-lookup"><span data-stu-id="c17dc-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="c17dc-112">Получает размер большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="c17dc-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c17dc-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c17dc-113">Return Value</span></span>  
 <span data-ttu-id="c17dc-114">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="c17dc-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c17dc-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c17dc-115">Requirements</span></span>  
 <span data-ttu-id="c17dc-116">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="c17dc-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c17dc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c17dc-117">See also</span></span>

- [<span data-ttu-id="c17dc-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="c17dc-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c17dc-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="c17dc-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c17dc-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="c17dc-120">ALink API</span></span>](index.md)
