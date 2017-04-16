---
title: "CorFlags.exe (CorFlags Conversion Tool) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "CorFlags conversion tool"
  - "CorFlags.exe"
  - "portable executable files, CorFlags section"
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# CorFlags.exe (CorFlags Conversion Tool)
Средство преобразования CorFlags позволяет настраивать раздел CorFlags в заголовке переносимого исполняемого образа.  
  
 Эта программа автоматически устанавливается вместе с Visual Studio.  Программу можно запустить из командной строки разработчика \(или из командной строки Visual Studio в Windows 7\).  Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 В командной строке введите следующее.  
  
## Синтаксис  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### Параметры  
  
|Обязательный параметр|Описание|  
|---------------------------|--------------|  
|`assembly`|Имя сборки, для которой требуется настроить раздел CorFlags.|  
  
|Параметр|Описание|  
|--------------|--------------|  
|**\/32BIT\[REQ\]\+**|Устанавливает флаг 32BITREQUIRED.|  
|**\/32BIT\[REQ\]\-**|Снимает флаг 32BITREQUIRED.|  
|**\/32BITPREF\+**|Устанавливает флаг 32BITPREFERRED.  Приложение выполняется как 32\-разрядный процесс даже на 64\-разрядных платформах.  Устанавливайте этот флаг только в EXE\-файлах.  Если флаг установлен для библиотеки DLL, она не загружается в 64\-разрядных процессах и создается исключение <xref:System.BadImageFormatException>.  Файл EXE с этим флагом можно загрузить в 64\-разрядный процесс.<br /><br /> Новый параметр [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].|  
|**\/32BITPREF\-**|Снимает флаг 32BITPREFERRED.<br /><br /> Новый параметр [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].|  
|**\/?**|Отображает синтаксис команд и параметров программы.|  
|**\/Force**|Выполняет принудительное обновление, даже если сборка имеет строгое имя. **Important:**  При обновлении сборки со строгим именем перед выполнением ее кода необходимо снова подписать сборку.|  
|**\/help**|Отображает синтаксис команд и параметров программы.|  
|**\/ILONLY\+**|Устанавливает флаг ILONLY.|  
|**\/ILONLY\-**|Снимает флаг ILONLY.|  
|**\/nologo**|Отключает отображение эмблемы Майкрософт при запуске.|  
|**\/RevertCLRHeader**|Задает версии заголовка CLR значение 2.0.|  
|**\/UpgradeCLRHeader**|Обновляет версию заголовка CLR до версии 2.5. **Note:**  Для оптимального выполнения сборок они должны иметь версию заголовка CLR 2.5.|  
  
## Заметки  
 Если другие параметры не заданы, средство преобразования CorFlags отображает флаги заданной сборки.  
  
## См. также  
 [Tools](../../../docs/framework/tools/index.md)   
 [64\-разрядные приложения](../../../docs/framework/64-bit-apps.md)   
 [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md)