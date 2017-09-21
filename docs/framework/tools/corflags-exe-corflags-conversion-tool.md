---
title: "CorFlags.exe (средство преобразования CorFlags)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
caps.latest.revision: 17
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 80fb48fc86d3010020a0a8a79bb2b4b7a6275368
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="corflagsexe-corflags-conversion-tool"></a>CorFlags.exe (средство преобразования CorFlags)
Средство преобразования CorFlags позволяет настраивать раздел CorFlags в заголовке переносимого исполняемого образа.  
  
 Эта программа автоматически устанавливается вместе с Visual Studio. Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика (или командной строкой Visual Studio в Windows 7). Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 В командной строке введите следующее.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Обязательный параметр|Описание|  
|------------------------|-----------------|  
|`assembly`|Имя сборки, для которой требуется настроить раздел CorFlags.|  
  
|Параметр|Описание|  
|------------|-----------------|  
|**/32BIT[REQ]+**|Устанавливает флаг 32BITREQUIRED.|  
|**/32BIT[REQ]-**|Снимает флаг 32BITREQUIRED.|  
|**/32BITPREF+**|Устанавливает флаг 32BITPREFERRED. Приложение выполняется как 32-разрядный процесс даже на 64-разрядных платформах. Устанавливайте этот флаг только в EXE-файлах. Если флаг установлен для библиотеки DLL, она не загружается в 64-разрядных процессах и создается исключение <xref:System.BadImageFormatException>. Файл EXE с этим флагом можно загрузить в 64-разрядный процесс.<br /><br /> Новый параметр [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].|  
|**/32BITPREF-**|Снимает флаг 32BITPREFERRED.<br /><br /> Новый параметр [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].|  
|**/?**|Отображает синтаксис команд и параметров программы.|  
|**/Force**|Выполняет принудительное обновление, даже если сборка имеет строгое имя. **Важно!** При обновлении сборки со строгим именем перед выполнением ее кода необходимо снова подписать сборку.|  
|**/help**|Отображает синтаксис команд и параметров программы.|  
|**/ILONLY+**|Устанавливает флаг ILONLY.|  
|**/ILONLY-**|Снимает флаг ILONLY.|  
|**/nologo**|Отключает отображение эмблемы Майкрософт при запуске.|  
|**/RevertCLRHeader**|Задает версии заголовка CLR значение 2.0.|  
|**/ UpgradeCLRHeader**|Обновляет версию заголовка CLR до версии 2.5. **Примечание.** Для оптимального выполнения сборок они должны иметь версию заголовка CLR 2.5 или выше.|  
  
## <a name="remarks"></a>Примечания  
 Если другие параметры не заданы, средство преобразования CorFlags отображает флаги заданной сборки.  
  
## <a name="see-also"></a>См. также  
 [Инструменты](../../../docs/framework/tools/index.md)   
 [64-разрядные приложения](../../../docs/framework/64-bit-apps.md)   
 [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

