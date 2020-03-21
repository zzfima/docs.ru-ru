---
title: Пример локализации гибридного приложения
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 69aa5ae145ffe378b7a4547e5a33826965bf7894
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111118"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a>Пример локализации гибридного приложения

В этом пошаговом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] показании показано, как локализовать элементы в гибридном приложении на базе Windows Forms.

В данном пошаговом руководстве представлены следующие задачи.

- Создание принимающего проекта Windows Forms.

- Добавление локализуемого содержимого.

- Включение локализации.

- Назначение идентификаторов ресурсов.

- Использование средства LocBaml для создания вспомогательной сборки.

Для полного перечисления кода задач, иллюстрированных в этом пошаговом шаге, [см.](https://go.microsoft.com/fwlink/?LinkID=160015)

Закончив, вы получите локализованное гибридное приложение.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения этого пошагового руководства требуются следующие компоненты:

- Visual Studio 2017

## <a name="creating-the-windows-forms-host-project"></a>Создание ведущего проекта Windows Forms

Первым шагом является создание проекта приложения Windows [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Forms и добавление элемента с контентом, который вы будете локализовать.

### <a name="to-create-the-host-project"></a>Создание ведущего проекта

1. Создайте проект приложения `LocalizingWpfInWf` **WPF** под названием .  (**Файл** > **новый** > **проект** > **Визуальный C или** **Визуальный Базовый** > **Классический настольный WPF** > **приложение**).

2. Добавьте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> элемент, вызванный `SimpleControl` в проект.

3. Используйте <xref:System.Windows.Forms.Integration.ElementHost> элемент управления, чтобы поместить `SimpleControl` элемент на форму. Для получения дополнительной информации [см.](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)

## <a name="adding-localizable-content"></a>Добавление локализуемого содержимого

Далее вы добавите элемент управления меткой Windows Forms и установите [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое элемента в локализуемую строку.

### <a name="to-add-localizable-content"></a>Добавление локализуемого содержимого

1. В **Solution Explorer**, дважды щелкните **SimpleControl.xaml,** чтобы открыть его в WPF Designer.

2. Установите содержимое <xref:System.Windows.Controls.Button> элемента управления, используя следующий код.

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. В **Solution Explorer**, дважды нажмите **Form1,** чтобы открыть его в Windows Forms Designer.

4. Откройте **Toolbox** и дважды щелкните **этикетку,** чтобы добавить элемент управления этикеткой в форму. Задайте для его свойства <xref:System.Windows.Forms.Control.Text%2A> значение `"Hello"`.

5. Нажмите **F5,** чтобы построить и запустить приложение.

     И `SimpleControl` элемент, и элемент управления отображением текста **"Hello".**

## <a name="enabling-localization"></a>Включение локализации

Конструктор Windows Forms предоставляет параметры для включения локализации во вспомогательной сборке.

### <a name="to-enable-localization"></a>Включение локализации

1. В **Solution Explorer**, дважды нажмите **Form1.cs,** чтобы открыть его в Windows Forms Designer.

2. В окне **Свойств** установить значение **локального** свойства формы. `true`

3. В окне **Свойства** установите стоимость **языковой** недвижимости на **испанский язык (Испания).**

4. В конструкторе Windows Forms выберите элемент управления label.

5. В окне **Свойств** установить <xref:System.Windows.Forms.Control.Text%2A> значение `"Hola"`свойства .

     Новый файл ресурсов с именем Form1.es-ES.resx будет добавлен в проект.

6. В **Solution Explorer**, правой кнопкой мыши **Form1.cs** и нажмите **View Code,** чтобы открыть его в редакторе кода.

7. Копируйте следующий `Form1` код в конструкторе, `InitializeComponent`предшествуя вызову.

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. В **Solution Explorer**, правой кнопкой **локализованияWpfInWf** и нажмите **Разгрузить проекта**.

     Название проекта помечено **(недоступно).**

9. Нажмите правой кнопкой **локализованияWpfInWf**, и нажмите **Edit LocalizingWpfWf.csproj**.

     Файл проекта откроется в редакторе кода.

10. Копируйте следующую строку в первую `PropertyGroup` в файле проекта.

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. Сохраните файл проекта и закройте его.

12. В **Solution Explorer**, правой кнопкой **локализованияWpfInWf** и нажмите **Reload Project**.

## <a name="assigning-resource-identifiers"></a>Назначение идентификаторов ресурсов

Вы можете сопоставить локализуемое содержимое со сборками ресурсов с помощью идентификаторов ресурсов. Приложение MsBuild.exe автоматически назначает идентификаторы ресурсов при указании опции. `updateuid`

### <a name="to-assign-resource-identifiers"></a>Назначение идентификаторов ресурсов

1. Из меню «Пуск» откройте командный запрос разработчика для визуальной студии.

2. Используйте приведенную ниже команду для назначения идентификаторов ресурсов вашему локализуемому содержимому.

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. В **Solution Explorer**, дважды щелкните **SimpleControl.xaml,** чтобы открыть его в редакторе кода. Вы увидите, `msbuild` что команда `Uid` добавила атрибут ко всем элементам. Это облегчает локализацию через назначение идентификаторов ресурсов.

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. Нажмите клавишу **F6**, чтобы построить решение.

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a>Использование LocBaml для создания вспомогательной сборки

Локализованное содержимое хранится в *спутниковой сборке*только для ресурсов. Используйте инструмент командной строки LocBaml.exe для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создания локализованной сборки для вашего содержимого.

### <a name="to-produce-a-satellite-assembly"></a>Создание вспомогательной сборки

1. Скопируйте файл LocBaml.exe в папку проекта obj\Debug. Для получения дополнительной информации [см.](how-to-localize-an-application.md)

2. В окне командной строки используйте приведенную ниже команду для извлечения строк ресурсов во временный файл.

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. Откройте файл temp.csv с Visual Studio или другим текстовым редактором. Замените `"Hello"` строку с `"Hola"`испанским переводом, .

4. Сохраните файл temp.csv.

5. Используйте приведенную ниже команду для создания локализованного файла ресурса.

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     Файл LocalizingWpfInWf.g.es-ES.resources создается в папке obj\Debug.

6. Используйте приведенную ниже команду для создания локализованной вспомогательной сборки.

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     Файл LocalizingWpfInWf.resources.dll создается в папке obj\Debug.

7. Скопируйте файл LocalizingWpfInWf.resources.dll в папку проекта bin\Debug\es-ES. Замените существующий файл.

8. Запустите файл LocalizingWpfInWf.exe, который находится в папке проекта bin\Debug. Не выполняйте повторную сборку приложения, чтобы не перезаписать вспомогательную сборку.

     В приложении выводятся локализованные строки вместо английских строк.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Локализация приложения](how-to-localize-an-application.md)
- [Пошаговое руководство. Локализация форм Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
