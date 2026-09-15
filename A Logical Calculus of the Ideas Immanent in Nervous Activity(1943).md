# A LOGICAL CALCULUS OF THE IDEAS IMMANENT IN NERVOUS ACTIVITY* (WARREN S. MCCULLOCH AND WALTER PITTS, 1943) 「신경 활동에 내재하는 개념들의 논리적 계산 체계」
## introduction
- All-or-none: 뉴런은 발화하거나 안 하거나 둘 중 하나 → 명제(참/거짓)로 대응 가능
- 공간적/시간적 합산(threshold): 단일 시냅스로는 부족, 충분한 수의 시냅스가 동시에(또는 근접 시간에) 흥분해야 발화 → 이게 논리식에서 AND/OR 구조로 표현됨
- 억제(inhibition)는 절대적 거부권: 억제성 시냅스가 하나라도 활성화되면 그 순간 발화를 무조건 막는다 (이건 나중에 "상대적 억제"와 동치임을 증명함, Theorem 4) → 논리식에서 NOT으로 표현됨
- circle(순환 경로) 문제: 신경망에는 순환 회로가 있어서 활동이 계속 반복(reverberate)될 수 있고, 이 때문에 "과거의 특정 시점"을 특정할 수 없게 됨 → 이걸 다루려면 재귀함수(recursive function) 개념이 필요하다
## The Theory: Nets Without Circles
---
### 가정
1. 뉴런의 활동은 ‘전부 아니면 전무(all-or-none)’ 과정이다.
2. 어떤 뉴런을 어느 시점에 활성화시키기 위해서는, 일정한 고정된 수의 시냅스가 ‘잠재적 합산 기간(period of latent addition)’ 동안 흥분되어야 한다. 그리고 이 필요한 시냅스의 수는 그 뉴런의 이전 활동 상태나 뉴런 내 위치와 관계없이 일정하다.
3. 신경계 내부에서 중요한 지연은 시냅스 지연(synaptic delay)뿐이다.
4. 어떤 억제성 시냅스(inhibitory synapse)가 활동하면, 그 시점에는 해당 뉴런의 흥분이 절대적으로 방지된다.
5. 신경망의 구조는 시간에 따라 변하지 않는다.
---
- E: 존재 ∃
- →: 함의(p -> q)
- P: 어떤 성질/술어
- S(P): 성질(property)'을 입력받아서 새로운 '성질'을 만들어내는 연산자/ P(x) = x는 3이다 / S(P)(x) = x의 predecessor가 3이다 / S(P)(4) = 참
- c₁, c₂, ... = 신경망의 개별 뉴런
- Nᵢ(t) = "뉴런 cᵢ가 시간 t에 발화한다"
- N₁, N₂, ...를 하나의 일반적인 N 계열로 취급해서, 많은 뉴런에 대한 긴 논리식을 변수/연산자로 압축한다.
                 신경망 𝒩
                    │
          ┌─────────┴─────────┐
          ↓                   ↓
    입력 뉴런들             내부 뉴런들
 N₁, N₂, ..., Nₚ       Nₚ₊₁, ..., Nₙ
          │                   │
          └────────┬──────────┘
                   ↓
          논리적 관계를 찾음
                   ↓
       Nᵢ(zᵢ) ↔ Prᵢ(N₁,...,Nₚ,zᵢ)
                   ↓
       이 논리식이 실제 신경망에서
             성립하는가?
             /         \
           YES          NO
            ↓            ↓
       realizable    S를 적용해봄
       (narrow)          ↓
                      Sⁿ(Prᵢ)
                         ↓
                     구현 가능?
                         ↓
                  realizable
                  (extended)