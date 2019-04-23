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
ms.openlocfilehash: a4c77ade46d2401e2499a94504808efd94f79f93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152156"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="0b635-102">Метод GetWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="0b635-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="0b635-103">Извлекает большой двоичный объект ресурса Win32.</span><span class="sxs-lookup"><span data-stu-id="0b635-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="0b635-104">Этот метод вызывается после задания параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="0b635-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b635-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b635-105">Syntax</span></span>  
  
```  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b635-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b635-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0b635-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="0b635-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="0b635-108">Файл токен, используемый для извлечения имени файла для использования при создании ресурс версии Win32</span><span class="sxs-lookup"><span data-stu-id="0b635-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="0b635-109">Значение TRUE, если файл является библиотекой DLL, false для EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="0b635-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="0b635-110">Необязательный значок для вставки в большой двоичный объект ресурса.</span><span class="sxs-lookup"><span data-stu-id="0b635-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="0b635-111">Получает большой двоичный объект ресурса.</span><span class="sxs-lookup"><span data-stu-id="0b635-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="0b635-112">Получает размер большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="0b635-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b635-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0b635-113">Return Value</span></span>  
 <span data-ttu-id="0b635-114">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="0b635-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b635-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0b635-115">Requirements</span></span>  
 <span data-ttu-id="0b635-116">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="0b635-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b635-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0b635-117">See also</span></span>

- [<span data-ttu-id="0b635-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="0b635-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="0b635-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="0b635-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="0b635-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="0b635-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
