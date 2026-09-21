# Activity 6: Six Degrees to Katún — A Breadth-First Search Networking Challenge
## Sessions 13
## Due date (mm/dd/yyyy): 09/27/2026
## ADRIANA ROSALES GONZÁLEZ
## Delivery Format: [] Video URL | [X] Markdown file | [] Jupyter Notebook file

---

# Activity Description

## The Story

You're a Business Development Associate at **Meridian Consulting Group**, trying to land a
meeting with **Elena Ruiz, CFO of Grupo Katún**. You don't know her directly — but maybe someone
you know, knows someone, who knows her. In business networking this is often called **"degrees
of separation"**: how many introductions stand between you and someone you want to meet. It's
exactly the idea behind LinkedIn's "2nd connection" / "3rd connection" labels.

You don't just want *a* chain of introductions — you want the **shortest one**. That's exactly
the problem **Breadth-First Search (BFS)** solves.

This activity is a single interactive app — no coding required. Everyone in the class uses the
**same fixed professional network** (there is no randomness anywhere in the app), so your
results should match your classmates' exactly.

**App link:** https://uam-aiclass-a6.streamlit.app/

If you'd rather run it on your own machine instead of using the shared link, see
**Running It Yourself** below.

### The App

The app has two tabs:

1. **🕸️ The Network** — the problem definition (initial state, goal state, actions, search
   space) and the full map of your professional network.
2. **🔎 BFS Path Finder** — click "Process next person in line" to watch Breadth-First Search
   work through the network one person at a time, using a first-in-first-out line (queue), until
   it reaches Elena Ruiz.

### Your Tasks

No programming background is required — just follow each step and use the hints if you get stuck.

1. **Read the Network tab.** Note the initial state, the goal state, and open "Who is who?" to
   understand each contact.
   
* You — Business Development Associate at Meridian Consulting Group. This is where your search starts.
* Marco Aguilar — Senior Account Manager at Meridian. One of your closest work contacts.
* Sofia Chan — Marketing Director at Meridian. Knows people across several client accounts.
* Diego Torres — Operations Lead at Meridian. Friendly, but his network doesn't extend beyond Marco.
* Valentina Cruz — Alumni Network Coordinator. A natural connector between different circles.
* Roberto Kim — Regional Sales VP at a partner firm.
* Camila Duarte — Independent Consultant who works with several manufacturing clients.
* Javier Mendez — Procurement Manager at Grupo Katún.
* Ana Beltran — Executive Assistant to the CFO at Grupo Katún.
* Elena Ruiz — CFO of Grupo Katún — the decision-maker you're ultimately trying to reach.

---

2. **Step through the BFS Path Finder tab, one click at a time, until Elena Ruiz is reached.**
3. **Find the step where someone had no new contacts to offer.** 

* Step 1
<img width="616" height="497" alt="Step_1" src="https://github.com/user-attachments/assets/6d6958a9-7696-4e9c-8d78-c5300a4950aa" />

* Step 2
<img width="626" height="500" alt="Step_2" src="https://github.com/user-attachments/assets/88787435-18e1-4e9b-a3f8-e5cacbfe1374" />

  
* Step 3
<img width="632" height="518" alt="Step_3" src="https://github.com/user-attachments/assets/65d91666-1dfc-4925-97e4-70d1152e28aa" />

  
* Step 4
<img width="605" height="505" alt="Step_4" src="https://github.com/user-attachments/assets/ba19201b-6fc2-4a47-a734-9927b12a132a" />

  
* Step 5
<img width="614" height="505" alt="Step_5" src="https://github.com/user-attachments/assets/1d54105b-0c11-43c4-bcdc-0b0a59051107" />


* Step 6
<img width="607" height="475" alt="Step_6" src="https://github.com/user-attachments/assets/8d0b9470-6fc3-4f1f-9f1d-91efb75938a0" />


* Step 7
<img width="611" height="530" alt="Step_7" src="https://github.com/user-attachments/assets/c35af126-7dd0-4a9c-b23a-370b17728f4b" />


* Step 8
<img width="608" height="449" alt="Step_8" src="https://github.com/user-attachments/assets/e7bc83b5-df7c-4a2e-bb3b-0c8f9a700945" />

---

4. **Take a screenshot of the final success message**

<img width="606" height="557" alt="Step_9_FINAL" src="https://github.com/user-attachments/assets/6ec71874-1682-40dd-ad71-b99d418f0eb4" />


5. **Open "What would last session's DFS have done here?"** and take a screenshot of the
   comparison.

6. **Fill out `A6_ReflectionQuestions.md`**, using the exact data from your run, and submit it
   along with your labeled screenshots.

### Running It Yourself (optional)

If you already completed Activity 2's setup and prefer to run this locally instead of using the
shared link:

```bash
conda activate ai_uam
cd Activity6
pip install -r requirements.txt
streamlit run app.py
```

# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)Ç



---


# Activity 6 — Reflection Questions: Six Degrees to Katún

**1. What is the **initial state** and the **goal state** in this activity?**
- The initial state is You, since the search begins from me. The goal state is Elena Ruiz, the CFO, who is the target of the introduction chain.

**2. List, in order, every person BFS **processed** (took from the front of the line) before reaching Elena Ruiz. How many people did it process in total?**

- In order, BFS processed:
You → Marco Aguilar → Sofia Chan → Diego Torres → Valentina Cruz → Roberto Kim → Camila Duarte → Javier Mendez → Ana Beltran → Elena Ruiz  
In total, it processed 10 people before stopping at Elena Ruiz.

**3. Name the one contact who had **no new introductions** to offer when BFS reached them. Based on the network, explain in one sentence why not.**

- The contact was Roberto Kim. He had no new introductions because all of his connections had already been reached earlier in the search, so he added nothing new to the queue.

**4. What is the exact **shortest chain of introductions** from You to Elena Ruiz, and how many introductions (hops) does it take?**

- The exact shortest chain was: You → Marco Aguilar → Valentina Cruz → Camila Duarte → Javier Mendez → Ana Beltran → Elena Ruiz. This required 6 hops (introductions).

**5. According to the "What would last session's DFS have done here?" comparison, how many introductions would DFS have needed on this exact same network? Is that more, fewer, or the same as BFS's result?**

- According to the app, DFS would have needed more introductions than BFS on this same network. BFS found the path in 6 hops, while DFS would have gone deeper into one branch before backtracking, increasing the number of steps.

**6. In your own words, explain why BFS is **guaranteed** to find the shortest chain of introductions, while DFS is not. Use the words **"line" (or "queue")** and **"stack"** somewhere in your answer.**

- BFS uses a line (queue), which means it always processes the closest neighbors first. That ensures the first time it reaches the goal, it is by the shortest path. DFS, on the other hand, uses a stack, diving deep into one branch regardless of distance, which can lead to finding a longer path before eventually backtracking.

**7. Name one **real business scenario** (other than this one) where finding the *fewest-hops* connection matters more than just finding *any* connection at all — for example, referral chains, supply-chain routing, or an approval/escalation chain. Briefly explain why the fewest-hops answer specifically matters there.**

- A good example is an approval chain in a company. In this case, finding the fewest hops matters because each additional step means more time and bureaucracy. The shortest path ensures that authorization is obtained quickly and efficiently, avoiding unnecessary delays.

