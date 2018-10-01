---
title: Winmdexp.exe (средство экспорта метаданных среды выполнения Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Runtime Metadata Export Tool
- Winmdexp.exe
ms.assetid: d2ce0683-343d-403e-bb8d-209186f7a19d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a228513bd29e35e8793124846de16f1c8bf4c10
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2018
ms.locfileid: "47237180"
---
# <a name="winmdexpexe-windows-runtime-metadata-export-tool"></a>Winmdexp.exe (средство экспорта метаданных среды выполнения Windows)
Программа экспорта метаданных (Winmdexp.exe) [!INCLUDE[wrt](../../../includes/wrt-md.md)] преобразует модуль .NET Framework в файл, содержащий метаданные [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Несмотря на то что сборки .NET Framework и файлы метаданных [!INCLUDE[wrt](../../../includes/wrt-md.md)] используют один и тот же физический формат, существуют различия в содержимом таблиц метаданных, то есть сборки .NET Framework невозможно автоматически использовать как компоненты [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Процесс преобразования модуля .NET Framework в компонент [!INCLUDE[wrt](../../../includes/wrt-md.md)] называется *экспортированием*. В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] и [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] конечный файл метаданных Windows (WINMD) содержит и метаданные, и реализацию.  
  
 При использовании шаблона **Компонент [!INCLUDE[wrt](../../../includes/wrt-md.md)]** из **Магазина Windows** для C# и Visual Basic в [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] или [!INCLUDE[vs_dev11_ext](../../../includes/vs-dev11-ext-md.md)] компилятор должен создать WINMDOBJ-файл, а на последующих этапах построения вызывается программа Winmdexp.exe, чтобы экспортировать WINMDOBJ-файл в WINMD-файл. Это рекомендуемый способ создания компонента [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Если над процессом построения требуется больший контроль по сравнению со средой Visual Studio, программу Winmdexp.exe следует вызывать напрямую.  
  
 Эта программа автоматически устанавливается вместе с Visual Studio. Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика (или командной строкой Visual Studio в Windows 7). Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 В командной строке введите следующее.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
winmdexp [options] winmdmodule  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Аргумент или параметр|Описание:|  
|------------------------|-----------------|  
|`winmdmodule`|Задает экспортируемый модуль (WINMDOBJ). Допускается только один модуль. Чтобы создать этот модуль, следует использовать параметр компилятора `/target` с целевым объектом `winmdobj`. См. статью [/target:winmdobj (параметры компилятора C#)](~/docs/csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md) или [/target (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/target.md).|  
|`/docfile:` `docfile`<br /><br /> `/d:` `docfile`|Задает выходной файл документации XML, который создаст программа Winmdexp.exe. В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] выходной файл совпадает со входным файлом XML документации.|  
|`/moduledoc:` `docfile`<br /><br /> `/md:` `docfile`|Задает имя файла документации XML, который компилятор создает с использованием `winmdmodule`.|  
|`/modulepdb:` `symbolfile`<br /><br /> `/mp:` `symbolfile`|Задает имя файла базы данных программы (PDB), содержащего символы для `winmdmodule`.|  
|`/nowarn:` `warning`|Отключает указанный номер предупреждения. В качестве *предупреждения* следует указать только числовую часть кода ошибки без предшествующих нулей.|  
|`/out:` `file`<br /><br /> `/o:` `file`|Задает имя выходного файла метаданных Windows (WINMD).|  
|`/pdb:` `symbolfile`<br /><br /> `/p:` `symbolfile`|Задает имя выходного файла базы данных программы (PDB), в котором будут указаны символы для экспортированного файла метаданных Windows (WINMD).|  
|`/reference:` `winmd`<br /><br /> `/r:` `winmd`|Задает файл метаданных (WINMD или сборку), на который необходимо ссылаться во время экспорта. Если используются ссылочные сборки в \Program Files (x86)\Reference Assemblies\Microsoft\Framework\\.NETCore\v4.5 (\Program Files\\... на 32-разрядных компьютерах), следует включить ссылки как на библиотеку System.Runtime.dll, так и на mscorlib.dll.|  
|`/utf8output`|Указывает, что выходные сообщения должны иметь кодировку UTF-8.|  
|`/warnaserror+`|Указывает, что все предупреждения должны рассматриваться как ошибки.|  
|**@** `responsefile`|Задает файл ответа (RSP), содержащий параметры (и при необходимости — `winmdmodule`). Каждая строка в файле `responsefile` должна содержать один аргумент или параметр.|  
  
## <a name="remarks"></a>Примечания  
 Программа Winmdexp.exe не предназначена для преобразования произвольной сборки .NET Framework в WINMD-файл. Для ее работы требуется модуль, который скомпилирован с параметром `/target:winmdobj`, и использование дополнительных ограничений. Наиболее важным ограничением является то, что все типы, которые отображаются в рабочей области API сборки, должны быть типами [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Дополнительные сведения см. в разделе "Объявление типов в компонентах среды выполнения Windows" статьи [Создание компонентов среды выполнения Windows на языках C# и Visual Basic](https://go.microsoft.com/fwlink/p/?LinkID=238313) в Центре разработки для Windows.  
  
 Платформа .NET Framework упрощает программирование в [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] и делает его более естественным при создании приложений [!INCLUDE[wrt](../../../includes/wrt-md.md)] или компонентов [!INCLUDE[wrt](../../../includes/wrt-md.md)] на C# или Visual Basic. Это рассматривается в статье [Поддержка платформы .NET Framework для приложений Магазина Windows и среды выполнения Windows](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md). Во время разработки некоторые часто используемые типы [!INCLUDE[wrt](../../../includes/wrt-md.md)] сопоставляются с типами .NET Framework. Программа Winmdexp.exe позволяет упростить такой процесс и создает рабочую область API, в которой используются соответствующие типы [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Например, типы, полученные из интерфейса <xref:System.Collections.Generic.IList%601>, сопоставляются с типами, полученными из интерфейса [!INCLUDE[wrt](../../../includes/wrt-md.md)][IVector\<T>](https://go.microsoft.com/fwlink/p/?LinkId=251132).  
  
## <a name="see-also"></a>См. также  
 [Поддержка платформы .NET Framework для приложений магазина Windows и среды выполнения Windows](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)  
 [Создание компонентов среды выполнения Windows в C# и Visual Basic](https://go.microsoft.com/fwlink/p/?LinkID=238313)  
 [Сообщения об ошибках Winmdexp.exe](../../../docs/framework/tools/winmdexp-exe-error-messages.md)  
 [Средства построения, развертывания и конфигурирования (платформа .NET Framework)](https://msdn.microsoft.com/library/b8c921be-6012-4181-b8d4-ab15813fc9a7)
