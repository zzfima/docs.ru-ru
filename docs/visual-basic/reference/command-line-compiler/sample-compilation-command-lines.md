---
title: "Примеры командных строк компиляции (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "командная строка, компиляторы"
  - "компиляция, командная строка"
  - "компиляторы, работающие в режиме командной строки"
  - "компиляция исходного кода, командная строка"
  - "компилятор Visual Basic, примеры команд командной строки"
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Примеры командных строк компиляции (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

В качестве альтернативы компиляции программ [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] из [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] можно компилировать из командной строки для создания исполняемого файла \(.exe\) или файлов библиотеки динамической компоновки \(.dll\).  
  
 Компилятор командной строки [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] поддерживает полный набор параметров для управления входными и выходными файлами, сборками, а также параметрами отладки и препроцессора.  Каждый параметр доступен в двух взаимозаменяемых формах:`-``option` и `/``option`.  В данном документе показана только форма `/``option`.  
  
 В следующей таблице представлен список примеров командных строк, которые можно изменять согласно необходимости.  
  
|Целевой тип|Применение|  
|-----------------|----------------|  
|Компиляция файла File.vb и создание файла File.exe|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|Компиляция файла File.vb и создание файла File.dll|`vbc /target:library File.vb`|  
|Компиляция файла File.vb и создание файла My.exe|`vbc /out:My.exe File.vb`|  
|Компиляция всех файлов [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] в текущем каталоге с включенной оптимизацией и определенным символом `DEBUG` для получения файла File2.exe|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|Компиляция всех файлов [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] в текущем каталоге, создание отладочной версии File2.dll без отображения эмблемы или предупреждений|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|Компиляция всех файлов [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] в текущем каталоге для получения файла Something.dll|`vbc /target:library /out:Something.dll *.vb`|  
  
 При компиляции из командной строки необходимо явным образом указать библиотеку времени выполнения Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] с помощью параметра компилятора `/reference`.  
  
> [!TIP]
>  При построении проекта с помощью интегрированной среды разработки Visual Studio, можно отобразить данные о связанной команду **vbc** с соответствующими параметрами компилятора в окне вывода.  Для отображения этих сведений откройте [Диалоговое окно "Параметры",  проекты и решения, сборка и запуск](/visual-studio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run) и присвойте свойству **Степень подробности сообщений при построении проекта MSBuild** значение **Обычный** или уровень детализации.  Для получения дополнительной информации см. [Практическое руководство. Просмотр, сохранение и настройка файлов журнала построения](../Topic/How%20to:%20View,%20Save,%20and%20Configure%20Build%20Log%20Files.md).  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)