# AwardsCollectionApp

Сейчас размеры ячеек для представления CustonGridView мы задаем непосредственно в самом представлении:

.frame(width: sideSize, height: sideSize)
 

Ширина и высота каждой ячейки равна ширине представления, деленное на количество столбцов.

Необходимо делегировать полномочия по установки размеров ячеек тому представлению, которе будет вызывать CustonGridView. Вызов должен выглядеть таким образом:

CustomGridView(items: activeAwards, columns: 2) { itemSize, award in
    VStack {
        award.awardView
        Text(award.title)
    }
    .padding()
    .frame(width: itemSize, height: itemSize)
}
