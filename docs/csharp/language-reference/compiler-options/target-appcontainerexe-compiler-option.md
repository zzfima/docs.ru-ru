---
title: "-target:appcontainerexe (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 61fc914b0d956bcca8e0d574296fa0723b0e1406
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2018
---
# <a name="-targetappcontainerexe-c-compiler-options"></a>-target:appcontainerexe (параметры компилятора C#)
Если используется параметр компилятора **-target:appcontainerexe**, компилятор создает исполняемый файл Windows (EXE-файл), который должен запускаться в контейнере приложения. Этот параметр аналогичен [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), но предназначен для приложений [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр устанавливает бит в [переносимом исполняемом](https://msdn.microsoft.com/library/windows/desktop/ms680547(v=vs.85).aspx?id=19509) файле (PE), чтобы обеспечить запуск приложения в контейнере. Если он установлен, при попытке запустить исполняемый файл вне контейнера приложения методом CreateProcess будет возникать ошибка.  
  
 Выходной файл получает имя входного файла, содержащего метод [Main](../../../csharp/programming-guide/main-and-command-args/index.md), если только с помощью параметра [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) не указано иное.  
  
 Если этот параметр указан в командной строке, все файлы до следующего параметра **-out** или **-target** будут использоваться для создания исполняемого файла.  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a>Установка данного параметра компилятора в интегрированной среде разработки  
  
1.  В **обозревателе решений** откройте контекстное меню своего проекта и выберите пункт **Свойства**.  
  
2.  На вкладке **Приложение** в списке **Тип выходных данных** выберите **Приложение для Магазина Windows**.  
  
     Этот параметр доступен только для шаблонов приложений под [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 Следующая команда компилирует `filename.cs` в исполняемый файл Windows, который может быть запущен только в контейнере приложения.  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a>См. также  
 [-target (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [-target:winexe (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)
