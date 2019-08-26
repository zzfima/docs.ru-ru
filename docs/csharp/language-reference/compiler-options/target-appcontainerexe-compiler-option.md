---
title: -target:appcontainerexe (параметры компилятора C#)
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: 09ae01d95138b72a0012f294189d288fc71c74b2
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606521"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a>-target:appcontainerexe (параметры компилятора C#)
Если используется параметр компилятора **-target:appcontainerexe**, компилятор создает исполняемый файл Windows (EXE-файл), который должен запускаться в контейнере приложения. Этот параметр аналогичен [-target:winexe](./target-winexe-compiler-option.md), но предназначен для приложений [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр устанавливает бит в [переносимом исполняемом](/windows/desktop/Debug/pe-format) файле (PE), чтобы обеспечить запуск приложения в контейнере. Если он установлен, при попытке запустить исполняемый файл вне контейнера приложения методом CreateProcess будет возникать ошибка.  
  
 Выходной файл получает имя входного файла, содержащего метод [Main](../../programming-guide/main-and-command-args/index.md), если только с помощью параметра [-out](./out-compiler-option.md) не указано иное.  
  
 Если этот параметр указан в командной строке, все файлы до следующего параметра **-out** или **-target** будут использоваться для создания исполняемого файла.  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a>Установка данного параметра компилятора в интегрированной среде разработки  
  
1. В **обозревателе решений** откройте контекстное меню своего проекта и выберите пункт **Свойства**.  
  
2. На вкладке **Приложение** в списке **Тип выходных данных** выберите **Приложение для Магазина Windows**.  
  
     Этот параметр доступен только для шаблонов приложений под [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  
 Следующая команда компилирует `filename.cs` в исполняемый файл Windows, который может быть запущен только в контейнере приложения.  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a>См. также

- [-target (параметры компилятора C#)](./target-compiler-option.md)
- [-target:winexe (параметры компилятора C#)](./target-winexe-compiler-option.md)
- [Параметры компилятора C# ](./index.md)
