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
ms.openlocfilehash: ff3103a46390c880a56ff443bfe20744f2ba0bfd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430688"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="2b4c3-102">Метод GetWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="2b4c3-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="2b4c3-103">Извлекает BLOB-объект ресурса Win32.</span><span class="sxs-lookup"><span data-stu-id="2b4c3-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="2b4c3-104">Вызовите этот метод после установки параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="2b4c3-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b4c3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b4c3-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2b4c3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b4c3-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2b4c3-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="2b4c3-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2b4c3-108">Токен файла, используемый для получения имени файла, используемого при создании ресурса версии Win32</span><span class="sxs-lookup"><span data-stu-id="2b4c3-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="2b4c3-109">Значение TRUE, если файл является библиотекой DLL, и false для EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="2b4c3-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="2b4c3-110">Необязательный значок для вставки в большой двоичный объект ресурса.</span><span class="sxs-lookup"><span data-stu-id="2b4c3-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="2b4c3-111">Получает большой двоичный объект ресурса.</span><span class="sxs-lookup"><span data-stu-id="2b4c3-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="2b4c3-112">Получает размер большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="2b4c3-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b4c3-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2b4c3-113">Return Value</span></span>  
 <span data-ttu-id="2b4c3-114">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="2b4c3-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b4c3-115">Требования</span><span class="sxs-lookup"><span data-stu-id="2b4c3-115">Requirements</span></span>  
 <span data-ttu-id="2b4c3-116">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="2b4c3-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b4c3-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2b4c3-117">See also</span></span>

- [<span data-ttu-id="2b4c3-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="2b4c3-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2b4c3-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="2b4c3-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2b4c3-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="2b4c3-120">ALink API</span></span>](index.md)
