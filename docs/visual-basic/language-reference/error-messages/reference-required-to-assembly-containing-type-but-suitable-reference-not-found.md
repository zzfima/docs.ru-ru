---
title: Требуется ссылка на сборку <assemblyidentity>, содержащую тип <typename>, но подходящую ссылку не удалось найти из-за неоднозначности между проектами <projectname1> и <projectname2>
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 3cfdf8150c8ccd9e1b4f047cd1ce8ee4ad6bbc1a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813409"
---
# <a name="reference-required-to-assembly-assemblyidentity-containing-type-typename-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-projectname1-and-projectname2"></a>Требуется ссылка на сборку "\<удостоверение_сборки >" содержащий тип "\<typename >", но подходящая ссылка не удалось найти из-за неоднозначности между проектами\<имя_проекта1 > "и"\< имя_проекта2 > "
Выражение использует тип, например класс, структуру, интерфейс, перечисление или делегат, который определен за пределами проекта. Однако имеются ссылки проекта на несколько сборок, определяющих этот тип.  
  
 Названные проекты создают сборки с тем же именем. Поэтому компилятор не может определить, какую сборку следует использовать для типа, к которому осуществляется доступ.  
  
 Чтобы получить доступ к типу, определенному в другой сборке, компилятор Visual Basic должен иметь ссылку на эту сборку. Это должна быть одна однозначная ссылка, не вызывающая циклических ссылок между проектами.  
  
 **Идентификатор ошибки:** BC30969  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Определите, какой проект создает наиболее подходящую сборку для проекта, чтобы ссылаться на нее в дальнейшем. Для этого можно использовать такие критерии, как простота доступа к файлам и частота обновления.  
  
2.  В свойствах проекта добавьте ссылку на файл, содержащий сборку, определяющую используемый тип.  
  
## <a name="see-also"></a>См. также

- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
- [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
- [Диагностика неработающих ссылок](/visualstudio/ide/troubleshooting-broken-references)
