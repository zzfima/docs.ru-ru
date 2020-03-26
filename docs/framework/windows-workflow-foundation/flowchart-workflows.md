---
title: Рабочие процессы блок-схемы
ms.date: 03/30/2017
ms.assetid: b0a3475c-d22f-49eb-8912-973c960aebf5
ms.openlocfilehash: b84b0de34f8869d9775fe0694e74c340cc16a6b3
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249068"
---
# <a name="flowchart-workflows"></a>Рабочие процессы блок-схемы

Блок-схемы лежат в основе широко известного принципа разработки программ. Действие «Блок-схема» обычно используется для реализации непоследовательных рабочих процессов, но если не требуются узлы `FlowDecision`, то может использоваться для реализации последовательных рабочих процессов.

## <a name="flowchart-workflow-structure"></a>Структура рабочего процесса Flowchart

 Действие Flowchart представляет собой действие, содержащее набор действий, которые будут выполнены.  Блок-схемы также содержат элементы управления потоком, такие как <xref:System.Activities.Statements.FlowDecision> и <xref:System.Activities.Statements.FlowSwitch%601>, контролирующие выполнение между содержащимися действиями на основании значений переменных.

## <a name="types-of-flow-nodes"></a>Типы узлов потока

 Используются различные типы элементов в зависимости от типа управления потока, требуемого при выполнении элемента. К типам элементов блок-схемы относятся следующие:

- `FlowStep` - моделирует один шаг выполнения в блок-схеме.

- `FlowDecision` - создает ветвь выполнения на основе логического условия, такого как <xref:System.Activities.Statements.If>.

- `FlowSwitch` - обеспечивает ветвление в ходе выполнения на основе переключателя с неперекрывающимися ветвями, такого как <xref:System.Activities.Statements.Switch%601>.

Каждая ссылка имеет свойство `Action`, определяющее действие <xref:System.Activities.ActivityAction>, которое может быть использовано для выполнения дочерних действий, а также одно или несколько свойств `Next`, которые определяют элемент или элементы, выполняемые после завершения выполнения текущего элемента.

### <a name="creating-a-basic-activity-sequence-with-a-flowstep-node"></a>Создание базовой последовательности активности с помощью узла FlowStep

Для моделирования базовой последовательности, в которой поочередно выполняются два действия, используется элемент `FlowStep`. В следующем примере используются два элемента `FlowStep` для последовательного выполнения двух действий.

```xml
<Flowchart>
  <FlowStep>
    <Assign DisplayName="Get Name">
      <Assign.To>
        <OutArgument x:TypeArguments="x:String">[result]</OutArgument>
      </Assign.To>
      <Assign.Value>
        <InArgument x:TypeArguments="x:String">["User"]</InArgument>
      </Assign.Value>
    </Assign>
    <FlowStep.Next>
      <FlowStep>
        <WriteLine Text="Hello, " & [result]/>
      </FlowStep>
    </FlowStep.Next>
  </FlowStep>
</Flowchart>
```

### <a name="creating-a-conditional-flowchart-with-a-flowdecision-node"></a>Создание условного потока с узлами FlowDecision

Чтобы смоделировать узел условного потока на блок-схеме рабочего процесса (т. е. создать ссылку, работающую аналогично символу принятия решения на стандартной блок-схеме), следует использовать узел <xref:System.Activities.Statements.FlowDecision>. Для свойства <xref:System.Activities.Statements.FlowDecision.Condition%2A> узла задано выражение, которое определяет условие, а для свойств <xref:System.Activities.Statements.FlowDecision.True%2A> и <xref:System.Activities.Statements.FlowDecision.False%2A> заданы экземпляры <xref:System.Activities.Statements.FlowNode>, которые будут выполняться, если результатом вычисления выражения будет `true` или `false`. В следующем примере показано определение рабочего процесса, который использует узел <xref:System.Activities.Statements.FlowDecision>.

```xml
<Flowchart>
  <FlowStep>
    <Read Result="[s]"/>
    <FlowStep.Next>
      <FlowDecision>
        <IsEmpty Input="[s]" />
        <FlowDecision.True>
          <FlowStep>
            <Write Text="Empty"/>
          </FlowStep>
        </FlowDecision.True>
        <FlowDecision.False>
          <FlowStep>
            <Write Text="Non-Empty"/>
          </FlowStep>
        </FlowDecision.False>
      </FlowDecision>
    </FlowStep.Next>
  </FlowStep>
</Flowchart>
```

### <a name="creating-an-exclusive-switch-with-a-flowswitch-node"></a>Создание эксклюзивного коммутатора с узлами FlowSwitch

Чтобы смоделировать блок-схему, в которой на основе соответствующего значения выбирается один из взаимоисключающих вариантов пути, используется узел <xref:System.Activities.Statements.FlowSwitch%601>. Свойство <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> имеет значение <xref:System.Activities.Activity%601> с параметром типа <xref:System.Object>, который определяет значение для сопоставления с выбираемыми элементами. Свойство <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> определяет словарь ключей и объектов <xref:System.Activities.Statements.FlowNode> для сопоставления с условным выражением и набор объектов <xref:System.Activities.Statements.FlowNode>, которые определяют направление выполнения в случае, если заданный вариант соответствует условному выражению. <xref:System.Activities.Statements.FlowSwitch%601> также определяет свойство <xref:System.Activities.Statements.FlowSwitch%601.Default%2A>, которое определяет направление выполнения при отсутствии соответствий условному выражению. В следующем примере показано, как определить рабочий процесс, который использует элемент <xref:System.Activities.Statements.FlowSwitch%601>.

```xml
<Flowchart>
  <FlowSwitch>
    <FlowStep x:Key="Red">
      <WriteRed/>
    </FlowStep>
    <FlowStep x:Key="Blue">
      <WriteBlue/>
    </FlowStep>
    <FlowStep x:Key="Green">
      <WriteGreen/>
    </FlowStep>
  </FlowSwitch>
</Flowchart>
```
