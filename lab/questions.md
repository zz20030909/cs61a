from operator import sub, mul

def make_anonymous_factorial():
    """Return the value of an expression that computes factorial.

    >>> make_anonymous_factorial()(5)
    120
    >>> from construct_check import check
    >>> # ban any assignments or recursion
    >>> check(SOURCE_FILE, 'make_anonymous_factorial',
    ...     ['Assign', 'AnnAssign', 'AugAssign', 'NamedExpr', 'FunctionDef', 'Recursion'])
    True
    """
    return (lambda f: f(f))(lambda f: lambda n: 1 if n == 1 else mul(n, f(f)(sub(n, 1))))
hw03一行流，离谱了


def balanced(t):
    """Checks if each branch has same sum of all elements and
    if each branch is balanced.

    >>> t = tree(1, [tree(3), tree(1, [tree(2)]), tree(1, [tree(1), tree(1)])])
    >>> balanced(t)
    True
    >>> t = tree(1, [t, tree(1)])
    >>> balanced(t)
    False
    >>> t = tree(1, [tree(4), tree(1, [tree(2), tree(1)]), tree(1, [tree(3)])])
    >>> balanced(t)
    False
    """
    "*** YOUR CODE HERE ***"
    if is_leaf(t):
        return True
    
    # 1. 拿到所有分支的总和
    # 这里用到了你之前写的 sum_tree 函数
    branch_sums = [sum_tree(b) for b in branches(t)]
    
    # 2. 检查条件 A：是不是所有分支的和都一样？
    # 这里的技巧是看：是不是每一个 sum 都等于列表里的第一个 sum
    all_sums_equal = all([s == branch_sums[0] for s in branch_sums])
    
    # 3. 检查条件 B：是不是每一个分支自己也平衡？
    # 递归调用 balanced 自身
    all_branches_balanced = all([balanced(b) for b in branches(t)])
    
    return all_sums_equal and all_branches_balanced
这是lab05，最后一题
