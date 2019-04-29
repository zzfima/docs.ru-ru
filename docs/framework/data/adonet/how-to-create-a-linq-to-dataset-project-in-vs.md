---
title: Создание проектов LINQ to DataSet в Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 22763d3b9581d09d7bdda0c09480f8d36bb8e2ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667055"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Практическое руководство. Создание проектов LINQ to DataSet в Visual Studio

Различные типы проектов LINQ требуются некоторые ссылки на сборки и импортируемых пространств имен (Visual Basic) или [с помощью](../../../csharp/language-reference/keywords/using-directive.md) директивы (C#). Минимальным требованием для LINQ — это ссылка на *System.Core.dll* и `using` директив для <xref:System.Linq>.

Эти требования предоставляются по умолчанию при создании C# консольного приложения проекта в Visual Studio 2017. Если вы обновляете проект с более ранней версии Visual Studio, может потребоваться вручную ввести эти ссылки, связанные с LINQ.

LINQ to DataSet требуются две дополнительные ссылки на *System.Data.dll* и *System.Data.DataSetExtensions.dll*.

> [!NOTE]
> Если вы выполняете сборку из командной строки, необходимо вручную указать связанные с LINQ библиотеки DLL в *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.

## <a name="to-enable-linq-to-dataset-functionality"></a>Включение функциональности LINQ to DataSet

Выполните следующие шаги для включения функциональных возможностей набора данных в существующий проект LINQ.

1. Добавьте ссылки на **System.Core**, **System.Data**, и **System.Data.DataSetExtensions**.

   В **обозревателе решений**, щелкните правой кнопкой мыши **ссылки** узел и выберите **добавить ссылку**. В **диспетчер ссылок** выберите **System.Core**, **System.Data**, и **System.Data.DataSetExtensions**. Нажмите кнопку **ОК**.

1. Добавить [с помощью](../../../csharp/language-reference/keywords/using-directive.md) директивы (или [инструкции импорта](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) в Visual Basic) для **System.Data** и **System.Linq**.

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. При необходимости добавьте `using` директивы (или `Imports` инструкции) для **System.Data.Common** или **System.Data.SqlClient**, в зависимости от способа подключения к базе данных.

## <a name="see-also"></a>См. также

- [Начало работы с LINQ to DataSet](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
