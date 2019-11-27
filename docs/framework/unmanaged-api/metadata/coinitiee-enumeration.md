---
title: Перечисление COINITIEE
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
ms.openlocfilehash: 2ccc038b4420040779dae70f15e3a8827ba94180
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444104"
---
# <a name="coinitiee-enumeration"></a>Перечисление COINITIEE
Указывает константы, используемые [CoInitialize](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) при инициализации среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|Режим инициализации по умолчанию. Это Инициализирует среду выполнения и создает <xref:System.AppDomain>по умолчанию.|  
|`COINITEE_DLL`|Инициализирует для запуска управляемой библиотеки DLL.|  
|`COINITEE_MAIN`|Инициализирует для запуска управляемого EXE-файла. Это Инициализирует среду выполнения, но не создает <xref:System.AppDomain>по умолчанию, который создается после ввода основной подпрограммы EXE-файла.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
