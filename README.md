<body>
    <div class="content-container"> 
        <div class="content">
            <h1>Tic Tac Toe with Feynman</h1>
            <hr>
            <h2>Motivation</h2>
            <p>
                The motivation behind making this project was as follows. From a very long time I was interested game development, I have found that the best way for me, to learn a new language or tool is to build a complete, working game with it.
            </p>
            <p>
                Qiskit was no different. I started learning it two years before I built this project. And this project was made in summer of 2025. When learning this language (obviously along with the theory of Quantum computing), I came across this <a href="https://youtu.be/U6_wSh_-EQc?si=k-DlE6ik6sIhTznl" target="_blank">video</a>. And this triggered me to make one of my own version. But one thing that disappointed me was that what they had made wasn't the usual tic tac toe. Most projects that i came across had implemented <a href="" target="_blank">Quantum Tic Tac Toe</a>, which is an entriely different game at all. I'm not saying their project was not impressive. If that was the case, I would never had tried making this one in the first place. But what I saw was an opportunity. "Is it possible to make a fully functional Tic Tac Toe game (the usual one) using quantum circuits?". And then started my journey of "Tic Tac Toe with Feynman". Also, I don’t claim this to be a unique idea; this is simply my attempt at creating it.
            </p>
            <p>
                Although, making this project did not take more than 10 days but this idea and the mental framework of how will I exactly implement the logic in the code took a very long time. In fact, more than a year. And it was a wonderful experience to build this project. 
            </p>
            <p>
                <b>I am writing about this project six months after I actually made it. Now I agree I see some flaws in the project and things that may seem impossible to implement via quantum computing, but this clarity of what’s possible and what’s not came only after I made the first attempt. So I hope it is understandable if my ideas sound immature.</b>
            </p>
            <hr>
            <h2>Ideas</h2>
            <p>
                Now it was about coming up with suitable ideas. In my mind I had a vague problem statement. And it was: let's say for a moment that the Tic-Tac-Toe program is created and let's assume it as a black box, then here is what I would want the black box to do. Arush is playing "X" and he makes the move. The board will then be converted to some numbers which will be then encoded into a qubit state. And then this qubit state goes into a quantum circuit.
                Now if I zoom out and look at any quantum circuit, I see that they take the initial state, apply some computation on the state and this can make the state no longer be the same one; in fact, the state can change into <b>multiple states at the same time</b>, and might proceed further into the quantum circuit.
                After the computation I measure the result and the state should be a classical bit string. Now when the bit state is converted to numbers and then when the numbers are again converted to a human-understandable Tic-Tac-Toe board, it should be such that the computer has played its move and now it's my turn to play my next move. So this was the idea.
            </p>
            <p>
                So when learning about quantum computing I came across two of the most famous quantum algorithms and they are Shor's Algorithm and Grover's Algorithm. Although at that time when I was thinking about making this game I knew about them, but was never able to understand them fully. This was also the time when I was making my own chess bot, and I knew that classical Tic-Tac-Toe engines used something called <b>Alpha-Beta Minimax Algorithm</b>. This, I believe, is an optimized version of something even more simple, which is the <b>British Museum Algorithm</b>. And the algorithm is very trivial and obvious to think of when making games like these. In simple words this algorithm makes a tree of all the possible next moves and all their consequences in the game, and then compares every branch, and picks the best move out of it.
            </p>
            <p>
                A simple example could be that I have the game of Tic-Tac-Toe and I made a blunder, so in the next move let’s say by placing an "X" at a certain location the computer is winning the game. Now the computer algorithm will place an "X" at all the locations possible and then will search for the best move. And there will certainly be a place where when "X" is placed the computer is winning, so it will pick that move from all the possible game states where the "X" was placed at places other than this, and will play the move (and also winning the game). This is British Meuseum Algorithm.
            </p>
            <p>
                Now if we think of this in terms of a quantum circuit, this is actually possible. From a basic understanding of quantum computing we know that a Hadamard gate can put the state of a qubit into superposition of all the possible states that the qubit can be in. So in the later section I will elaborate on how I tried to implement this idea to make the game tree using quantum gates.
            </p>
            <p>
                Assuming we can form a superposition of all possible board states after I play "O" (that is, all board states resulting from placing "X" in every legal position), this is the stage where Grover’s Algorithm becomes necessary.
            </p>
            <p>
                After creating the superposition of all the states, I could actually construct the second layer of the tree, which involves determining where to make my next move. This could be achieved by further applying the Hadamard gate in some clever ways. However, this was not what I originally had in mind back then. For now, I have only explored the first depth of the tree. (If you are familier with chess engines, it means to have the depth of chess engine set to 1 for analysis)
            </p>
            <hr>
            <p>
                For detailed explanation about the code you can visit my github page <a href="" target="_blanck">Here</a>
            </p>
</body>
</html>
