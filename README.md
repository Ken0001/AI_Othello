# AI_Othello
107-1_NDHU_AI_Final Project
### Othello
>This is an Othello board. 

     a b c d e f g h      X: Black
     . . . . . . . .  1   O: White
     . . . . . . . .  2   ?: Able to move
     . . . ? . . . .  3
     . . ? O X . . .  4
     . . . X O ? . .  5
     . . . . ? . . .  6
     . . . . . . . .  7
     . . . . . . . .  8



### Minimax Algorithm With Alpha-Beta Pruning
>Minmax Algorithm的原理
是一種悲觀算法，假設對手每一步都會將我方引入從當前看理論上價值最小的格局方向，即對手具有完美決策能力。因此我方的策略應該是選擇那些對方所能達到的讓我方最差情況中最好的，也就是讓對方在完美決策下所對我造成的損失最小。Minmax不會找理論最佳解，因為理論最佳解會取決於對手是否足夠愚蠢。所以如果對方走出完美決策，那我方可以達到預計最小損失的格局；反之對方決策若不完美， 我方則可能達到比預計情況更好的結局。
      
     
```javascript 
function minimax(node, depth, α, β, maxPlayer)
    if node is a terminal node or depth = 0
        return the value of node
    if maxPlayer
        v := +∞
        foreach child of node
            v := min(v, minimax(child, depth-1, α, β, FALSE))
            α := max(α, v)
            if β ≤ α     break
        return v
    else 
        v := +∞
        foreach child of node
            v := min(v, minimax(child, depth-1, α, β, TRUE))
            β := max(β, v)
            if β ≤ α     break
        return v
```
### Board Grade
> Each position on the board will have a score, which is determined by the weight. 
> These scores are used as nodes value for the Minmax algorithm.

### Board Weight

<table>
<tr align=center>
<font face="Consolas" size=3 color=#DC143C>
<td>a</td><td>b</td><td> c</td><td>  d</td><td>  e</td><td> f</td><td>g</td><td>h</td><td></td>
</font>
</tr>
<tr align=center bgcolor="FFFFFF"><td>100</td><td>-10</td><td> 10</td><td>  5</td><td>  5</td><td> 10</td><td>-10</td><td>100</td><td>  1</td></tr>
<tr align=center><td>-10</td><td>-20</td><td> -5</td><td> -1</td><td> -1</td><td> -5</td><td>-20</td><td>-10</td><td>  2</td></tr>
<tr align=center><td> 10</td><td> -5</td><td>  5</td><td>  2</td><td>  2</td><td>  5</td><td> -5</td><td> 10</td><td>  3</td></tr>
<tr align=center><td>  5</td><td> -1</td><td>  2</td><td>  0</td><td>  0</td><td>  2</td><td> -1</td><td>  5</td><td>  4</td></tr>
<tr align=center><td>  5</td><td> -1</td><td>  2</td><td>  0</td><td>  0</td><td>  2</td><td> -1</td><td>  5</td><td>  5</td></tr>
<tr align=center><td> 10</td><td> -5</td><td>  5</td><td>  2</td><td>  2</td><td>  5</td><td> -5</td><td> 10</td><td>  6</td></tr>
<tr align=center><td>-10</td><td>-20</td><td> -5</td><td> -1</td><td> -1</td><td> -5</td><td>-20</td><td>-10</td><td>  7</td></tr>
<tr align=center><td>100</td><td>-10</td><td> 10</td><td>  5</td><td>  5</td><td> 10</td><td>-10</td><td>100</td><td>  8</td></tr></font>
</table>
