---
layout: post
title: Java - Laugh or Cry, Your Choice...
---

Sometimes I’ll come across something in Java that baffles me. I’m not
saying there is a better way to do this in any other language. Maybe
someone will show the solution in their language of passion.

So, I’ll I want to do is get the difference between one ArrayList and
another. And, only one way. Nothing hard about that. So, I thought. The
first problem semi-stickler is that I have to get rid of all duplicates
first…to make to the diff cleaner. In order to do this (order not a
factor) is go from an ArrayList to a HashSet. You can see the rest
below. There has to be a better way.

    <code>
    import java.util.ArrayList;
    import java.util.HashSet;
    import java.util.Iterator;


    public class HashTest {

        /**
         * @param args
         */
        public static void main(String[] args) {
            // TODO Auto-generated method stub
            ArrayList<String> aList = new ArrayList<String>();
            ArrayList<String> bList = new ArrayList<String>();

            aList.add("xxx");
            aList.add("yyy");
            aList.add("zzz");
            aList.add("zzz");

            bList.add("xxx");
            bList.add("yyy");
            bList.add("yyy");
            bList.add("aaa");

            HashSet<String> aHash = new HashSet<String>(aList);
            HashSet<String> bHash = new HashSet<String>(bList);

            Iterator<String> aIter = aHash.iterator();
            Iterator<String> bIter = bHash.iterator();

            while (aIter.hasNext()) {
                System.out.println("A: " + aIter.next());
            }

            while (bIter.hasNext()) {
                System.out.println("B: " + bIter.next());
            }

            HashSet<String> diffHash = new HashSet<String>();
            diffHash = aHash;
            diffHash.removeAll(bHash);

            Iterator<String> diffIter = aHash.iterator();
            while (diffIter.hasNext()) {
                System.out.println("A DIFF: " + diffIter.next());
            }
        }
    }
    </code>
