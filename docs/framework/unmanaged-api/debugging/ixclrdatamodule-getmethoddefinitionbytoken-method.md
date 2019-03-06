---
title: Метод IXCLRDataModule::GetMethodDefinitionByToken
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 727005437289b4bc66ab90f280b80a79f4db06db
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359319"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a>Метод IXCLRDataModule::GetMethodDefinitionByToken

Возвращает определение метода, соответствующей токену метаданных.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a>Параметры

`token`\
[in] Маркер метода.

`methodDefinition`\
[out] Определение метода.

## <a name="remarks"></a>Примечания

Указанный метод является частью `IXCLRDataModule` интерфейса и соответствует 25 слот в таблице виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
**Заголовок.** Нет  
**Библиотека:** Нет  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
 
## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс IXCLRDataModule](ixclrdatamodule-interface.md)
