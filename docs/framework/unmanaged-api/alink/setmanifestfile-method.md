---
title: Метод SetManifestFile
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b293c30060107d18c6b609efc82c4128a73cc1c7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787209"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="72826-102">Метод SetManifestFile</span><span class="sxs-lookup"><span data-stu-id="72826-102">SetManifestFile Method</span></span>
<span data-ttu-id="72826-103">Позволяет указать или сбросить файл манифеста, используемый компоновщиком при создании сборки.</span><span class="sxs-lookup"><span data-stu-id="72826-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72826-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72826-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="72826-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="72826-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="72826-106">Имя файла манифеста, содержимое которого помещается в большой двоичный объект Win32 Resources.</span><span class="sxs-lookup"><span data-stu-id="72826-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72826-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="72826-107">Return Value</span></span>  
 <span data-ttu-id="72826-108">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="72826-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72826-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="72826-109">Remarks</span></span>  
 <span data-ttu-id="72826-110">Вызовите этот метод, прежде чем запрашивать Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="72826-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="72826-111">Значение `pszFile` параметра — это имя файла манифеста, содержимое которого считывается и помещается в ресурсы Win32 с идентификатором RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="72826-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="72826-112">При вызове с помощью параметра NULL все ранее прочитанные манифесты очищаются.</span><span class="sxs-lookup"><span data-stu-id="72826-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="72826-113">Это позволяет сбросить состояние компоновщика до значения времени инициализации.</span><span class="sxs-lookup"><span data-stu-id="72826-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72826-114">Требования</span><span class="sxs-lookup"><span data-stu-id="72826-114">Requirements</span></span>  
 <span data-ttu-id="72826-115">Требуется aLink. h</span><span class="sxs-lookup"><span data-stu-id="72826-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72826-116">См. также</span><span class="sxs-lookup"><span data-stu-id="72826-116">See also</span></span>

- [<span data-ttu-id="72826-117">Интерфейс IALink3</span><span class="sxs-lookup"><span data-stu-id="72826-117">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="72826-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="72826-118">ALink API</span></span>](index.md)
- [<span data-ttu-id="72826-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="72826-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="72826-120">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="72826-120">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
