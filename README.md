# limitviewpager
自定义viewpager

Question:

NullPointerException异常的dispatchDraw与ViewPager嵌套的片段，PageTransformer(Nullpointerexception on dispatchDraw with ViewPager in nested fragment with PageTransformer)


Answer:

1：

@Override

public void draw(Canvas canvas) {

    try {
    
        super.draw(canvas);
        
    } catch (NullPointerException e) {
    
        Log.d("ViewPager", "Nullpointer skipped");
        
    }
    
}


2:（解决方式）


public class TestViewPager extends ViewPager {

    public TestViewPager(Context context) {
        super(context);
    }

    public TestViewPager(Context context, AttributeSet attrs) {
        super(context, attrs);
    }

    @Override
    protected int getChildDrawingOrder(int childCount, int i) {
        return i;
    }

}
