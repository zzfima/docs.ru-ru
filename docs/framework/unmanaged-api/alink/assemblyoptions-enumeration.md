---
title: "Перечисление AssemblyOptions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyOptions
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ccbbcabd3fbb372322ca6334f6ab6db4fdafc2f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="assemblyoptions-enumeration"></a>Перечисление AssemblyOptions
Перечисляет параметры сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>Поля  
  
|Поле|Описание|  
|-----------|-----------------|  
|optAssemTitle|Строка — определяет название сборки.|  
|optAssemDescription|Строка — содержит описание сборки.|  
|optAssemConfig|Строка — содержит конфигурацию сборки.|  
|optAssemOS|Строка - кодировке: «dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion».|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Строка — содержит языковой стандарт сборки.|  
|optAssemVersion|Строка - кодировке: «Основной_номер.дополнительный_номер.сборка.редакция».|  
|optAssemCompany|Строка — содержит компании.|  
|optAssemProduct|Строка — содержит имя продукта.|  
|optAssemProductVersion|Строка (также известный как InformationalVersion).|  
|optAssemCopyright|Строка — содержит сведения об авторских правах.|  
|optAssemTrademark|Строка — содержит сведения о товарном знаке.|  
|optAssemKeyFile|Строка (имя файла).|  
|optAssemKeyName|Строка (имя ключа).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Значение типа bool (также называется DelaySign).|  
|optAssemFileVersion|Строка - кодируется как «Основной_номер.дополнительный_номер.сборка.редакция» — то же, что ProductVersion.|  
|optAssemSatelliteVer|Строка - кодируется как «Основной_номер.дополнительный_номер.сборка.редакция».|  
|optLastAssemOption|Счетчик числа элементов.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** alink.h  
  
 **Библиотека**: alink.dll  
  
## <a name="see-also"></a>См. также  
 [Al.exe (компоновщик сборок)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
