# Masnory-

#### 更简洁的方式： dividedBy的用法
```
/**
 Masonry比例用法

 @param model <#model description#>
 */
- (void)setModel:(QCTtodoContentTableViewCellModel *)model{
    _model = model;
    
    // 构建子试图
//    CGFloat *w = [self]
    QCTsubStatusBtnView * lasttmp;
    NSInteger col = 4;
    for (int i = 0; i<col; model.models) {
        QCTtodoStatusInfoModel *obj = model.models[i];
        QCTsubStatusBtnView * tmp = [QCTsubStatusBtnView new];
        tmp.model = obj;
        
        [self addSubview:tmp];
        __weak __typeof__(self) weakSelf = self;

        [tmp mas_makeConstraints:^(MASConstraintMaker *make) {
            make.centerY.equalTo(weakSelf);
//            tmp
            
            
            make.width.equalTo(weakSelf).dividedBy(col);
//            make.left.equalTo(tmp.mas_width).multipliedBy(i);
            
            if (i%col == 0) {
                make.left.equalTo(weakSelf);

            }else{
                make.left.equalTo(lasttmp.mas_right);

            }
            
//            make.centerX.equalTo(tmp.mas_width).multipliedBy(i*2+1);

            make.bottom.equalTo(weakSelf);
            make.top.equalTo(weakSelf);
        }];
        
        lasttmp = tmp;
        i++;

        
        
    }
    
}

```
