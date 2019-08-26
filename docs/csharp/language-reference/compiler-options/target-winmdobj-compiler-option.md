---
title: -target:winmdobj (параметры компилятора C#)
ms.date: 07/20/2015
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
ms.openlocfilehash: fe1332f9ed6de9c50c2509e29f22ed7c0e57ade9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606356"
---
# <a name="-targetwinmdobj-c-compiler-options"></a>-target:winmdobj (параметры компилятора C#)
Если используется параметр компилятора **-target:winmdobj**, компилятор создает промежуточный WINMDOBJ-файл, который можно преобразовать в двоичный WINMD-файл среды выполнения Windows. Затем WINMD-файл можно использовать в программах на языках JavaScript и C++ в дополнение к программам, использующим управляемые языки.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-target:winmdobj  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр **winmdobj** сигнализирует компилятору, что необходим промежуточный модуль. В результате Visual Studio компилирует библиотеку классов C# в виде WINMDOBJ-файла. Затем WINMDOBJ-файл можно обработать с помощью инструмента экспорта <xref:Microsoft.Build.Tasks.WinMDExp> для создания файла метаданных Windows (WINCMD-файл). WINMD-файл содержит код из исходной библиотеки и метаданные WinMD, используемые JavaScript, C++ и средой выполнения Windows.  
  
 Выходные данные файла, скомпилированного с помощью параметра **-target:winmdobj**, предназначены только для использования в качестве входных данных инструментом экспорта WimMDExp (на WINMDOBJ-файл нет прямой ссылки).  
  
 Выходной файл получает имя первого входного файла, если только с помощью параметра [-out](./out-compiler-option.md) не указано иное. Метод [Main](../../programming-guide/main-and-command-args/index.md) не требуется.  
  
 Если параметр -target:winmdobj указан в командной строке, все файлы до следующего параметра **-out** или [-target:module](./target-module-compiler-option.md) будут использоваться для создания программы Windows.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a>Установка данного параметра компилятора в интегрированной среде разработки Visual Studio для приложения для Магазина Windows  
  
1. В **обозревателе решений** откройте контекстное меню своего проекта и выберите пункт **Свойства**.  
  
2. Перейдите на вкладку **Приложение**.  
  
3. В списке **Тип выходных данных** выберите **Файл WinMD**.  
  
     Параметр **Файл WinMD[!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] доступен только для шаблонов приложений для** .  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 Следующая команда компилирует `filename.cs` в промежуточный WINMDOBJ-файл.  
  
```console  
csc -target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a>См. также

- [-target (параметры компилятора C#)](./target-compiler-option.md)
- [Параметры компилятора C# ](./index.md)
