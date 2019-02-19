---
title: Динамическое создание и компиляция исходного кода
ms.date: 03/30/2017
helpviewer_keywords:
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8feb94f3d57c25d634bd51b8f41eca42d5e5757a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220313"
---
# <a name="dynamic-source-code-generation-and-compilation"></a>Динамическое создание и компиляция исходного кода
В среду .NET Framework включен механизм, который называется Code Document Object Model (CodeDOM). Он позволяет разработчикам программ, порождающих исходный код, создавать код на нескольких языках программирования во время выполнения на основе единой модели, представляющей код для визуализации.  
  
 Для представления исходного кода элементы CodeDOM связываются друг с другом, образуя структуру данных, известную как граф CodeDOM, которая моделирует структуру некоторого исходного кода.  
  
 Пространство имен `System.CodeDom` определяет типы, с помощью которых логическая структура исходного кода может быть представлена независимо от конкретного языка программирования. Пространство имен `System.CodeDom.Compiler` определяет типы, используемые для формирования исходного кода на основе графов CodeDOM и управления компиляцией исходного кода на поддерживаемых языках. Набор поддерживаемых языков может быть расширен разработчиками или поставщиками компиляторов.  
  
 Независимое от языка моделирование исходного кода может быть полезно, если программа должна создавать исходный код для модели программы на нескольких языках или если конечный язык заранее не определен. Например, некоторые конструкторы используют модель CodeDOM в качестве интерфейса абстракции от языка для получения исходного кода на требуемом языке программирования, если имеется поддержка CodeDOM для этого языка.  
  
 В платформе .NET Framework имеются генераторы и компиляторы кода для языков <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider> и <xref:Microsoft.VisualBasic.VBCodeProvider>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Использование CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 Описываются общие случаи применения, а также демонстрируется создание простого графа объектов с использованием CodeDOM.  
  
 [Создание исходного кода и компиляция программы из графа CodeDOM](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)  
 Описание способов формирования исходного кода и его компиляции внешним компилятором с использованием классов, определенных в пространстве имен `System.CodeDom.Compiler`.  
  
 [Практическое руководство. Создание XML-файла документации с использованием CodeDOM](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md)  
 Описание использования CodeDOM для формирования кода с комментариями к XML-документации и компиляции сформированного кода для создания XML-документации.  
  
 [Практическое руководство. Создание класса с помощью CodeDOM](../../../docs/framework/reflection-and-codedom/how-to-create-a-class-using-codedom.md)  
 Описание использования CodeDOM для создания класса, содержащего поля, свойства, метод, конструктор и точку входа.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.CodeDom>  
 Определяет элементы, представляющие элементы кода на языках программирования, предназначенных для среды CLR.  
  
 <xref:System.CodeDom.Compiler>  
 Определяет интерфейсы для формирования и компиляции кода во время выполнения.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Краткий справочник по CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100))  
 Предоставляет разработчикам быстрый способ поиска элементов CodeDOM, представляющих элементы исходного кода.
