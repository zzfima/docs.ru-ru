---
title: Функция CreateHistoryReader
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
ms.openlocfilehash: 80979f0424469bb1d4771ad6507bb8c9d5364ab4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108609"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="88736-102">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="88736-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="88736-103">Создает средство чтения журнала для указанного файла.</span><span class="sxs-lookup"><span data-stu-id="88736-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88736-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88736-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="88736-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="88736-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="88736-106">окне Путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="88736-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="88736-107">заполняет При успешном завершении содержит указатель на средство чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="88736-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88736-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="88736-108">Return Value</span></span>  
 <span data-ttu-id="88736-109">Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError. h, а также значения, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="88736-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="88736-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="88736-110">Return code</span></span>|<span data-ttu-id="88736-111">Описание</span><span class="sxs-lookup"><span data-stu-id="88736-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="88736-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="88736-112">S_OK</span></span>|<span data-ttu-id="88736-113">Указывает, что метод успешно завершен.</span><span class="sxs-lookup"><span data-stu-id="88736-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="88736-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="88736-114">E_INVALIDARG</span></span>|<span data-ttu-id="88736-115">Указывает, что для `wzFilePath` или `ppHistoryReader` задана пустая ссылка.</span><span class="sxs-lookup"><span data-stu-id="88736-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88736-116">Требования</span><span class="sxs-lookup"><span data-stu-id="88736-116">Requirements</span></span>  
 <span data-ttu-id="88736-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88736-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88736-118">**Библиотека:** Fusion. dll</span><span class="sxs-lookup"><span data-stu-id="88736-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="88736-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88736-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88736-120">См. также</span><span class="sxs-lookup"><span data-stu-id="88736-120">See also</span></span>

- [<span data-ttu-id="88736-121">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="88736-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
