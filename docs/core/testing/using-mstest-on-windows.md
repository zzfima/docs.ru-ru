---
title: "Использование MSTest с .NET Core в Windows"
description: "Использование MSTest с .NET Core в Windows с помощью Visual Studio 2015"
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 08/18/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
translationtype: Human Translation
ms.sourcegitcommit: 6795f1ace77e6f4d1b2fe07e6281f4acb6d21271
ms.openlocfilehash: 11faa46347b18240e9ddf1c27f27a814103e2565

---

# <a name="unit-testing-with-mstest-and-net-core-on-windows-using-visual-studio-2015"></a>Модульное тестирование с помощью MSTest и .NET Core в Windows с использованием Visual Studio 2015

Хотя xUnit может быть более подходящим средством при нацеливании на несколько платформ, при использовании .NET Core в Windows можно также применять MSTest.

## <a name="prerequisites"></a>Предварительные требования

Создайте проект библиотеки, выполнив инструкции в разделе [Начало работы с .NET Core в Windows](../tutorials/using-on-windows.md).

### <a name="writing-the-test-project-using-mstest"></a>Написание тестового проекта с помощью MSTest

1. В обозревателе решений в контекстном меню узла **Решение** выберите **Добавить**, **Создать папку решения**. Присвойте папке имя test. 
   Это всего лишь папка решения, но не физическая папка.

2. Откройте контекстное меню папки **test** и выберите пункт **Добавить**, **Новый проект**. В диалоговом окне **Новый проект** выберите **Консольное приложение (.NET Core)**. Присвойте приложению имя TestLibrary и явным образом поместите его по пути `Golden\test`. 

   > [!IMPORTANT]
   > Проект должен быть консольным приложением, а не библиотекой классов.

3. В проекте **TestLibrary** откройте контекстное меню узла **Ссылки** и выберите пункт **Добавить ссылку**. 

4. В диалоговом окне **Диспетчер ссылок** установите флажок **Библиотека** в узле **Проекты**, **Решение**, а затем нажмите кнопку **ОК**. 

5. В проекте **TestLibrary** откройте файл `project.json` и замените `"Library": "1.0.0-*"` на `"Library": {"target": "project"}`. 

   Это позволит избежать разрешения проекта `Library` в пакет NuGet с тем же именем. Явное задание project в качестве целевого объекта позволяет гарантировать, что средства сначала будут искать проект с данным именем, а не пакет. 

6. Откройте контекстное меню узла **Ссылки** и выберите пункт **Управление пакетами NuGet**.

7. Выберите nuget.org в качестве **источника пакета** и перейдите на вкладку **Обзор**. Установите флажок **Включить предварительные выпуски**, найдите **MSTest.TestFramework** предварительной версии 1.0.1 или более поздней, а затем нажмите кнопку **Установить**. 

8. Найдите **dotnet-test-mstest** предварительной версии 1.1.1 или более поздней, а затем нажмите кнопку **Установить**.

9. Отредактируйте файл `project.json`, добавив `"testRunner": "mstest",` после раздела `"version"`.

10. Добавьте файл класса `LibraryTests.cs` в проект **TestLibrary**, добавьте директивы `using` `Microsoft.VisualStudio.TestTools.UnitTesting;` и `using Library;` в начало файла и добавьте в класс следующий код:
    ```csharp
    [TestClass]
    public class LibraryTests
    {
        [TestMethod]
        public void ThingGetsObjectValFromNumber()
        {
            Assert.AreEqual(42, new Thing().Get(42));
        }
    }
    ```
    * При необходимости удалите файл `Program.cs` из проекта **TestLibrary** и удалите `"buildOptions": {"emitEntryPoint": true},` из файла `project.json`.

   Теперь вы можете выполнить сборку решения. 
   
11. В меню **Тест** выберите **Windows**, **Обозреватель тестов**, а затем в обозревателе тестов выберите **Запустить все**.
   
   Тест должен быть пройден успешно.



<!--HONumber=Nov16_HO3-->


