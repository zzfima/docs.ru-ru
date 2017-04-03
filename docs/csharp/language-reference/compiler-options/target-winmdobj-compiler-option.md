---
title: "/target:winmdobj (параметры компилятора C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7581ec18db0d2741452b47ad6200482b63c102be
ms.lasthandoff: 03/13/2017

---
# <a name="targetwinmdobj-c-compiler-options"></a>/target:winmdobj (параметры компилятора C#)
Если используется параметр компилятора **/target:winmdobj**, компилятор создает промежуточный WINMDOBJ-файл, который можно преобразовать в бинарный WINMD-файл среды выполнения Windows. Затем WINMD-файл можно использовать в программах на языках JavaScript и C++ в дополнение к программам, использующим управляемые языки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/target:winmdobj  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр **winmdobj** сигнализирует компилятору, что необходим промежуточный модуль. В результате Visual Studio компилирует библиотеку классов C# в виде WINMDOBJ-файла. Затем WINMDOBJ-файл можно обработать с помощью инструмента экспорта <xref:Microsoft.Build.Tasks.WinMDExp> для создания файла метаданных Windows (WINCMD-файл). WINMD-файл содержит код из исходной библиотеки и метаданные WinMD, используемые JavaScript, C++ и средой выполнения Windows.  
  
 Выходные данные файла, скомпилированного с помощью параметра **/target:winmdobj**, предназначены только для использования в качестве входных данных инструментом экспорта WimMDExp (на WINMDOBJ-файл нет прямой ссылки).  
  
 Выходной файл получает имя первого входного файла, если только с помощью параметра [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) не указано иное. Метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md) не требуется.  
  
 Если параметр /target:winmdobj указан в командной строке, все файлы до следующего параметра **/out** или [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) будут использоваться для создания программы Windows.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a>Установка данного параметра компилятора в интегрированной среде разработки Visual Studio для приложения для Магазина Windows  
  
1.  В **обозревателе решений** откройте контекстное меню своего проекта и выберите пункт **Свойства**.  
  
2.  Перейдите на вкладку **Приложение**.  
  
3.  В списке **Тип выходных данных** выберите **Файл WinMD**.  
  
     Параметр **Файл WinMD[!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)] доступен только для шаблонов приложений для**.  
  
 Сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 Следующая команда компилирует `filename.cs` в промежуточный WINMDOBJ-файл.  
  
```  
csc /target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a>См. также  
 [/target (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
