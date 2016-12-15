---
title: "Построение из командной строки (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "сборки [Visual Basic], командная строка"
  - "компилятор Visual Basic, сведения о компиляторе Visual Basic"
  - "командная строка [Visual Basic], компиляторы"
  - "командная строка [Visual Basic], сборка из"
  - "командная строка [Visual Basic], сборки"
  - "компиляторы, вызов из командной строки"
  - "построение из командной строки"
  - "компиляция исходного кода"
  - "компиляторы, работающие в режиме командной строки, Visual Basic"
  - "командная строка [Visual Basic], Visual Basic"
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Построение из командной строки (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Проект [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] состоит из одного или нескольких исходных файлов.  В процессе компиляции эти файлы соединяются в один пакет — исполняемый файл, который запускается как приложение.  
  
 В качестве альтернативы компилятору в интегрированной среде разработки \(IDE\) [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] используется компилятор командной строки [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Компилятор командной строки разработан для случаев, когда нет необходимости в полном наборе средств, предоставляемых интерфейсом IDE — например, при использовании или создании программы на компьютере с ограниченными системными ресурсами или дисковым пространством.  
  
 При компиляции из командной строки необходимо явным образом указать библиотеку времени выполнения Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] с помощью параметра компилятора `/reference`.  
  
 Для компиляции исходных файлов из интегрированной среды разработки [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] используется команда **Построение** из меню **Построение**.  
  
> [!TIP]
>  При построении проекта файлы с помощью интегрированной среды разработки Visual Studio, можно отобразить данные о связанной команде **vbc** и его параметры в окне вывода.  Для отображения этих сведений откройте [Диалоговое окно "Параметры",  проекты и решения, сборка и запуск](/visual-studio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run) и присвойте свойству **Степень подробности сообщений при построении проекта MSBuild** значение **Обычный** или уровень детализации.  Для получения дополнительной информации см. [Практическое руководство. Просмотр, сохранение и настройка файлов журнала построения](../Topic/How%20to:%20View,%20Save,%20and%20Configure%20Build%20Log%20Files.md).  
  
 Можно компилировать файлы проекта \(с расширением VBPROJ\) в командной строке с помощью MSBuild.  Дополнительные сведения см. в разделах [Справочник по командной строке](/visual-studio/msbuild/msbuild-command-line-reference) и [Пошаговое руководство. Использование MSBuild](../Topic/Walkthrough:%20Using%20MSBuild.md).  
  
## В этом подразделе  
 [Практическое руководство. Вызов компилятора командной строки](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 Вызов компилятора командной строки из приглашения MS\-DOS или из определенного подкаталога.  
  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 Список примеров командных строк, которые можно изменять по необходимости.  
  
## Связанные подразделы  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 Список параметров компилятора, организованный в алфавитном порядке или по способу применения.  
  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 Способы компиляции отдельных частей кода.  
  
 [Построение и очистка проектов и решений в Visual Studio](/visual-studio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 Организация состава отдельных сборок, изменение свойств проекта и проверка правильности порядка построения проектов.