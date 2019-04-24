function shipIterate(ship1, ship2) {
    let alph = ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"]
    let arr =[]
    arr.push(ship1)
    arr.push(ship2)
    let y1 = parseInt(ship1.replace(/[^0-9]+/g, ''))
    let y2 = parseInt(ship2.replace(/[^0-9]+/g, ''))
    while (y1 !== y2) {
	arr.push((y1+1) + ship1[ship1.length - 1])
  	y1 += 1
    }
    let x1 = alph.indexOf(ship1[ship1.length - 1])
    let x2 = alph.indexOf(ship2[ship2.length - 1])
    while (x1 !== x2) {
        arr.push(ship1.replace(/[^0-9]+/g, '') + alph[x1 + 1])
       	x1 += 1
    }
    return arr;
}

function solution(N, S, T) {
    let hit = 0;
    let sunk = 0;
    let shipArr = []
    let ships = S.split(',')
    for (let i = 0; i < ships.length; i++) {
        let ship = ships[i].split(" ")
        if (ship[0] === ship[1]) {
            shipArr.push([ship[0]])
            ships.splice(i, 1)
        } else {
            shipArr.push(shipIterate(ship[0], ship[1]))
	}
    }
    let tArr = T.split(" ")

    for (let i = 0; i < shipArr.length; i ++) {
        if (shipArr[i].every(x => tArr.indexOf(x) !== -1)) {
            sunk += 1
        } else if (shipArr[i].find(x => tArr.indexOf(x) !== -1)) {
            hit += 1
        }
    }

    return `${sunk},${hit}`
}
