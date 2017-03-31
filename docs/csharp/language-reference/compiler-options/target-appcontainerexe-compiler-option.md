---
title: "-target:appcontainerexe (параметры компилятора C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
caps.latest.revision: 13
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
ms.openlocfilehash: 168771506692308bc9b031df5c059e58e8d190b1
ms.lasthandoff: 03/13/2017

---
# <a name="targetappcontainerexe-c-compiler-options"></a>/target:appcontainerexe (параметры компилятора C#)
Если используется параметр компилятора **/target:appcontainerexe**, компилятор создает исполняемый файл Windows (EXE-файл), который должен запускаться в контейнере приложения. Этот параметр аналогичен [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), но предназначен для приложений [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/target:appcontainerexe  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр устанавливает бит в [переносимом исполняемом](http://go.microsoft.com/fwlink/p/?LinkId=236960) файле (PE), чтобы обеспечить запуск приложения в контейнере. Если он установлен, при попытке запустить исполняемый файл вне контейнера приложения методом CreateProcess будет возникать ошибка.  
  
 Выходной файл получает имя входного файла, содержащего метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md), если только с помощью параметра [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) не указано иное.  
  
 Если этот параметр указан в командной строке, все файлы до следующего параметра **/out** или **/target** будут использоваться для создания исполняемого файла.  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a>Установка данного параметра компилятора в интегрированной среде разработки  
  
1.  В **обозревателе решений** откройте контекстное меню своего проекта и выберите пункт **Свойства**.  
  
2.  На вкладке **Приложение** в списке **Тип выходных данных** выберите **Приложение для Магазина Windows**.  
  
     Этот параметр доступен только для шаблонов приложений под [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)].  
  
 Сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 Следующая команда компилирует `filename.cs` в исполняемый файл Windows, который может быть запущен только в контейнере приложения.  
  
```  
csc /target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a>См. также  
 [/target (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [/target:winexe (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)   
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
