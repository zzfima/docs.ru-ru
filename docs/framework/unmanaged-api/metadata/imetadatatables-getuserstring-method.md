---
title: Метод IMetaDataTables::GetUserString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0fefbab6b2ea9fbbfd90e03c41578a924f99c7a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645205"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="8b7c0-102">Метод IMetaDataTables::GetUserString</span><span class="sxs-lookup"><span data-stu-id="8b7c0-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="8b7c0-103">Получает жестко заданную строку по указанному индексу в строковый столбец в текущей области.</span><span class="sxs-lookup"><span data-stu-id="8b7c0-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b7c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b7c0-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="8b7c0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b7c0-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="8b7c0-106">[in] Значение индекса, из которого извлекается строка жестко.</span><span class="sxs-lookup"><span data-stu-id="8b7c0-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="8b7c0-107">[out] Указатель на размер `ppData`.</span><span class="sxs-lookup"><span data-stu-id="8b7c0-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="8b7c0-108">[out] Указатель на указатель возвращаемой строки.</span><span class="sxs-lookup"><span data-stu-id="8b7c0-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="8b7c0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8b7c0-109">Requirements</span></span>

<span data-ttu-id="8b7c0-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b7c0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="8b7c0-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8b7c0-111">**Header:** Cor.h</span></span>

<span data-ttu-id="8b7c0-112">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b7c0-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="8b7c0-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b7c0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8b7c0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8b7c0-114">See also</span></span>

- [<span data-ttu-id="8b7c0-115">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="8b7c0-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="8b7c0-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="8b7c0-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)