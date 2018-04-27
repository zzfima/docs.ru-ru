---
title: Требуется ссылка на сборку &#39; &lt;assemblyidentity&gt; &#39; содержащий тип &#39; &lt;typename&gt;&#39;, но подходящая ссылка не удалось найти из-за неоднозначности между проекты &#39; &lt;имя_проекта1&gt; &#39; и &#39; &lt;имя_проекта2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69b1184d47e427bd985c3b18135d4a0ac4d91410
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a>Требуется ссылка на сборку &#39; &lt;assemblyidentity&gt; &#39; содержащий тип &#39; &lt;typename&gt;&#39;, но подходящая ссылка не удалось найти из-за неоднозначности между проекты &#39; &lt;имя_проекта1&gt; &#39; и &#39; &lt;имя_проекта2&gt;&#39;
Выражение использует тип, например класс, структуру, интерфейс, перечисление или делегат, который определен за пределами проекта. Однако имеются ссылки проекта на несколько сборок, определяющих этот тип.  
  
 Названные проекты создают сборки с тем же именем. Поэтому компилятор не может определить, какую сборку следует использовать для типа, к которому осуществляется доступ.  
  
 Для доступа к типу, определенному в другой сборке, компилятор Visual Basic должен иметь ссылку на эту сборку. Это должна быть одна однозначная ссылка, не вызывающая циклических ссылок между проектами.  
  
 **Идентификатор ошибки:** BC30969  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите, какой проект создает наиболее подходящую сборку для проекта, чтобы ссылаться на нее в дальнейшем. Для этого можно использовать такие критерии, как простота доступа к файлам и частота обновления.  
  
2.  В свойствах проекта добавьте ссылку на файл, содержащий сборку, определяющую используемый тип.  
  
## <a name="see-also"></a>См. также  
 [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)  
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)  
 [Диагностика неработающих ссылок](/visualstudio/ide/troubleshooting-broken-references)
