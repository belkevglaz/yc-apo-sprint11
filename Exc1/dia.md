```plantuml
@startuml LAYOUT_TOP_DOWN
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

' Settings
skinparam componentStyle rectangle
SHOW_PERSON_OUTLINE()

'skinparam linetype ortho
'skinparam linetype polyline
'!pragma layout smetana
LAYOUT_TOP_DOWN()

scale 0.8

title "Медикаменте" С4 Container diagram
top to bottom direction

'  Customization
AddBoundaryTag(dash, $borderStyle=DottedLine(), $shape=RoundedBoxShape(), $borderColor="#b8b8b8")

AddElementTag("extPerson", $bgColor="#999999")

AddElementTag("microservice", $shape=RoundedBoxShape(), $bgColor="CornflowerBlue", $fontColor="white", $legendText="microservice")
AddElementTag("storage", $shape=RoundedBoxShape(), $bgColor="lightSkyBlue", $fontColor="white", $legendText="storage")
AddElementTag("queue", $shape=RoundedBoxShape(), $bgColor="#b6ccde", $fontColor="white", $legendText="event sourcing")


Person(customer, "Пациент", $tags = "extPerson")

Container(dwh, "DWH", "MS SQL Server", "Хранит данные по клиентам,\nмедицинские карты,\nфинансовую историю,\nсчета,\nданные по персоналу больницы,\nи многое другое")

@enduml
```