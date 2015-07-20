# MCPP
training mcpp
package edu.mcpp.Alist;

public class LList1 implements ExList 
{
	class Node
	{
		int data;
		Node next = null;
		public Node(int val)
		{
			data = val;
		}
	}

	Node root = null;

	@Override
	public int size() 
	{
		int ret = 0;
		Node tnp = root;		
		while(tnp != null)
		{
			ret++;
			tnp = tnp.next;
		}			
		return ret;
	}

	@Override
	public void clear() 
	{
		root = null;
	}

	@Override
	public int[] toArray() 
	{
		int[] ret = new int[size()];
		Node tmp = root;		
		for (int i = 0; tmp != null; i++)
		{
			ret[i] = tmp.data;
			tmp = tmp.next;
		}			
		return ret;
	}

	@Override
	public void init(int[] mas) 
	{ 
		clear();
		if(mas == null)
			mas = new int[0];
		for  (int i = mas.length-1; i >= 0; i--)
		{			
			addStart(mas[i]);
		}
	}

	@Override
	public void addEnd(int val) 
	{
		Node tmp = new Node(val);

		if(root == null)
		{
			root = tmp;
			return;
		}

		Node rez = root;
		while (rez.next != null)
		{
			rez = rez.next;
		}
		rez.next = tmp;
	}

	@Override
	public void addStart(int val) 
	{
		if(root == null)
		{
			root = new Node(val);
			return;
		}
		Node tnp = new Node(val);
		tnp.next = root;
		root = tnp;
	}

	@Override
	public void addPos(int pos, int val) 
	{
		if  (pos > size() || pos < 0)			
			throw new IllegalArgumentException();

		Node tmp = new Node(val);
		if(root == null)
		{
			root = tmp;
			return;
		}
		if(pos == 0)
		{
			tmp.next = root;
			root = tmp;
		}
		Node rez_1 = root;
		Node rez_2;
		for (int i = 1; i < pos; i++)
		{
			rez_1 = rez_1.next;
		}
		rez_2 = rez_1.next;
		rez_1.next = tmp;
		tmp.next = rez_2;		
	}

	@Override
	public int delEnd() 
	{		
		if(root == null)
			throw new IllegalArgumentException();				

		if(root.next == null)
		{
			int end = root.data;
			root = null;
			return end;
		}

		Node rez = root;
		while (rez.next.next != null)
		{
			rez = rez.next;
		}
		int end = rez.next.data;
		rez.next = null;		
		return end;
	}

	@Override
	public int delStart() 
	{
		if(root == null)
			throw new IllegalArgumentException();	

		int start = root.data;
		root = root.next;
		return start;
	}

	@Override
	public int delPos(int pos) 
	{
		if(root == null || pos >= size() || pos < 0)
			throw new IllegalArgumentException(); 

		if(pos == 0)
		{
			int delpos = root.data;
			root = root.next;
			return delpos;
		}
		Node rez_1 = root;
		Node rez_2;
		for (int i = 1; i < pos; i++)
		{
			rez_1 = rez_1.next;
		}

		rez_2 = rez_1.next;
		int delpos = rez_2.data;
		rez_1.next = rez_2.next;
		return delpos;
	}

	@Override
	public int max() 
	{
		if ( size() == 0)
			throw new IllegalArgumentException();

		int max = root.data; 
		Node rez_1 = root;
		for (int i = 0; i < size(); i++)
		{
			if ( max < rez_1.data)
			{
				max = rez_1.data;
			}
			rez_1 = rez_1.next;
		}
		return max;
	}

	@Override
	public int min() 
	{
		if ( size() == 0)
			throw new IllegalArgumentException();

		int min = root.data; 
		Node rez_1 = root;
		for (int i = 0; i < size(); i++)
		{
			if ( min > rez_1.data)
			{
				min = rez_1.data;
			}
			rez_1 = rez_1.next;
		}
		return min;
	}

	@Override
	public int maxIndex() 
	{
		if ( size() == 0)
			throw new IllegalArgumentException();

		int maxind = 0; 
		int max = root.data; 
		Node rez_1 = root;
		for (int i = 0; i < size(); i++)
		{
			if ( max < rez_1.data)
			{
				max = rez_1.data;
				maxind = i;
			}
			rez_1 = rez_1.next;
		}
		return maxind;
	}

	@Override
	public int minIndex() 
	{
		if ( size() == 0)
			throw new IllegalArgumentException();

		int minind = 0; 
		int min = root.data; 
		Node rez_1 = root;
		for (int i = 0; i < size(); i++)
		{
			if ( min > rez_1.data)
			{
				min = rez_1.data;
				minind = i;
			}
			rez_1 = rez_1.next;
		}
		return minind;
	}

	@Override
	public void sort() 
	{
		if ( size() == 0 )
			throw new IllegalArgumentException();

		int[] tmp = toArray();
		for(int i = size() - 1 ; i > 0 ; i--)
		{
			for(int j = 0 ; j < i ; j++)
			{
				if( tmp[j] > tmp[j+1] )
				{
					int x = tmp[j];
					tmp[j] = tmp[j+1];
					tmp[j+1] = x;
				}
			}
		}
		init(tmp);
	}

	@Override
	public void reverse() 
	{
		if ( size() == 0 )
			throw new IllegalArgumentException();

		int[] tmp = toArray();
		int b = 0;
		for (int i = 0; i < (size())/2; i++)
		{
			b = tmp[i];
			tmp[i] = tmp[size() - 1 - i];
			tmp[size() - 1 - i] = b;
		}
		init(tmp);
	}

	@Override
	public void halfReverse() 
	{
		if ( size() == 0 )
			throw new IllegalArgumentException();

		int[] tmp = toArray();
		int b = 0;
		for (int i = 0; i < (size())/2; i++)
		{
			b = tmp[i];
			tmp[i] = tmp[(size() + 1)/2 + i];
			tmp[(size() + 1)/2 + i] = b;
		}
		init(tmp);

	}

	@Override
	public void set(int pos, int val) 
	{
		if (pos < 0 || pos >= size())
			throw new ArrayIndexOutOfBoundsException();

		if(pos == 0)
		{
			root.data = val;
			return;
		}
		Node rez_1 = root;
		for (int i = 0; i < pos; i++)
		{
			rez_1 = rez_1.next;
		}
		rez_1.data = val;
	}

	@Override
	public int get(int pos) 
	{
		if (pos < 0 || pos >= size())
			throw new IllegalArgumentException();

		if(pos == 0)
		{
			return root.data;
		}
		Node rez_1 = root;
		for (int i = 0; i < pos; i++)
		{
			rez_1 = rez_1.next;
		}
		return rez_1.data;
	}
}
