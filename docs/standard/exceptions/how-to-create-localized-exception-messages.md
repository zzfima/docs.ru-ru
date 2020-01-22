---
title: Создание пользовательских исключений с локализованными сообщениями об исключениях
description: Узнайте, как создавать пользовательские исключения с локализованными сообщениями.
author: Youssef1313
dev_langs:
- csharp
- vb
ms.date: 09/13/2019
ms.openlocfilehash: 9360fccf27a0900d8380461e03baa5806ce1e0da
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708922"
---
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a>Создание пользовательских исключений с локализованными сообщениями об исключениях

Из этой статьи вы узнаете, как создавать пользовательские исключения, унаследованные от базового класса <xref:System.Exception>, с локализованными сообщениями о них с использованием вспомогательных сборок.

## <a name="create-custom-exceptions"></a>Создание пользовательских исключений

.NET содержит множество различных исключений, которые можно использовать. Но в некоторых случаях, когда ни одно из них не соответствует вашим потребностям, вы можете создавать собственные пользовательские исключения.

Предположим, что нужно создать `StudentNotFoundException`, содержащее свойство `StudentName`.
Чтобы создать пользовательское исключение, сделайте следующее:

1. Создайте сериализуемый класс, который наследует от <xref:System.Exception>. Имя класса должно заканчиваться на Exception:

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception { }
    ```
    
    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception
    End Class
    ```

1. Добавьте конструкторы по умолчанию:

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }
    }
    ```
    
    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception

        Public Sub New()
        End Sub

        Public Sub New(message As String)
            MyBase.New(message)
        End Sub

        Public Sub New(message As String, inner As Exception)
            MyBase.New(message, inner)
        End Sub
    End Class
    ```

1. Определите любые дополнительные свойства и конструкторы:

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public string StudentName { get; }

        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }

        public StudentNotFoundException(string message, string studentName)
            : this(message)
        {
            StudentName = studentName;
        }
    }
    ```

    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception

        Public ReadOnly Property StudentName As String

        Public Sub New()
        End Sub

        Public Sub New(message As String)
            MyBase.New(message)
        End Sub

        Public Sub New(message As String, inner As Exception)
            MyBase.New(message, inner)
        End Sub

        Public Sub New(message As String, studentName As String)
            Me.New(message)
            StudentName = studentName
        End Sub
    End Class
    ```

## <a name="create-localized-exception-messages"></a>Создание локализованных сообщений об исключениях

Вы создали пользовательское исключение и можете вызывать его где угодно с помощью кода, подобного следующему:

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
```

```vb
Throw New StudentNotFoundException("The student cannot be found.", "John")
```

Проблема с предыдущей строкой заключается в том, что `"The student cannot be found."` — это просто константная строка. В локализованном приложении вам необходимо иметь разные сообщения в зависимости от языка и региональных параметров пользователя.
Это можно сделать с помощью [вспомогательных сборок](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md). Вспомогательная сборка — это библиотека DLL, содержащая ресурсы для определенного языка. При запросе конкретных ресурсов во время выполнения среда CLR находит этот ресурс в зависимости от языка и региональных параметров пользователя. Если вспомогательная сборка не найдена для этого языка и региональных параметров, используются ресурсы языка и региональных параметров по умолчанию.

Чтобы создать локализованные сообщения об исключениях:

1. Создайте папку с именем *Ресурсы* для хранения файлов ресурсов.
1. Добавьте в нее новый файл ресурсов. Для этого в Visual Studio щелкните правой кнопкой мыши папку в **обозревателе решений** и выберите **Добавить** > **Новый элемент** > **Файл ресурсов**. Присвойте файлу имя *ExceptionMessages.resx*. Это файл ресурсов по умолчанию.
1. Добавьте пару "имя/значение" для сообщения об исключении, как показано на следующем рисунке:

   ![Добавление ресурсов в язык и региональные параметры по умолчанию](media/add-resources-to-default-culture.jpg)

1. Добавьте новый файл ресурсов для французского языка. Присвойте ему имя *ExceptionMessages.fr-FR.resx*.
1. Снова добавьте пару "имя/значение" для сообщения об исключении, но со значением французского языка:

   ![Добавление ресурсов в язык и региональные параметры fr-FR](media/add-resources-to-fr-culture.jpg)

1. После сборки проекта папка выходных данных сборки должна содержать папку *fr-FR* с файлом *DLL*, который является вспомогательной сборкой.
1. Исключение вызывается с помощью кода, подобного приведенному ниже.

    ```csharp
    var resourceManager = new ResourceManager("FULLY_QIALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly());
    throw new StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John");
    ```

    > [!NOTE]
    > Если имя проекта — `TestProject`, а файл ресурсов *ExceptionMessages.resx* находится в папке *Ресурсы* проекта, полное имя файла ресурсов — `TestProject.Resources.ExceptionMessages`.

## <a name="see-also"></a>См. также

- [Как создать пользовательские исключения](how-to-create-user-defined-exceptions.md)
- [Создание вспомогательных сборок для приложений для настольных систем](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [base (справочник по C#)](../../csharp/language-reference/keywords/base.md)
- [this (справочник по C#)](../../csharp/language-reference/keywords/this.md)
