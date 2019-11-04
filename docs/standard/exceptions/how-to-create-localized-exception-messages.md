---
title: Пошаговое руководство. Создание пользовательских исключений с локализованными сообщениями об исключениях
description: Узнайте, как создавать пользовательские исключения с локализованными сообщениями.
author: Youssef1313
ms.date: 09/13/2019
ms.openlocfilehash: 453e332541628770932da2a6802fdcaee5211a84
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141523"
---
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a>Пошаговое руководство. Создание пользовательских исключений с локализованными сообщениями об исключениях

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

## <a name="create-localized-exception-messages"></a>Создание локализованных сообщений об исключениях

Вы создали пользовательское исключение и можете вызывать его где угодно с помощью кода, подобного следующему:

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
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
- [Creating Satellite Assemblies for Desktop Apps](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) (Создание вспомогательных сборок для классических приложений)
- [base (справочник по C#)](../../csharp/language-reference/keywords/base.md)
- [this (справочник по C#)](../../csharp/language-reference/keywords/this.md)
